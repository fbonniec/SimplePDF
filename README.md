<p align="center">
    <img src="./Assets/simple_pdf_logo.png" alt="Simple PDF" />
</p>

SimplePDF is a wrapper of UIGraphics PDF context written in Swift. 

You can: 
- [x] add texts, images, spaces and lines
- [x] set up page layout, adjust content alignment
- [x] generate PDF data/file.

In summary, you can create a simple PDF effortlessly. :smile:

## Example

```swift
let A4paperSize = CGSize(width: 595, height: 842)
let pdf = SimplePDF(pageSize: A4paperSize)

pdf.addText("Hello World!")
pdf.addImage( anImage )

let pdfData = pdf.generatePDFdata() 

// save as a local file
try? pdfData.writeToFile(path, options: .DataWritingAtomic)
``` 

See the result [example.pdf](Assets/example.pdf), which is generated from [ExampleCode.swift](ExampleCode.Swift).

## Installation

via [Cocoapods](https://cocoapods.org)

```ruby
use_frameworks!
pod 'SimplePDF'
```

## Usage

```swift
import SimplePDF
```

### Page Setup

![page setup](Assets/page_setup.png)

```swift
let A4paperSize = CGSize(width: 595, height: 842)
let pdf = SimplePDF(pageSize: A4paperSize, pageMargin: 20.0)
```

### Write Something

```swift
pdf.addText( "some text" )
pdf.addImage( UIImage )
pdf.addAttributedText( NSAttributedString )
pdf.addLineSeparator(height: 30) // or pdf.addLineSeparator() default height is 1.0
pdf.addLineSpace(20)
```

### Utilities

```swift
pdf.beginNewPage() // Begin a new page
```

These following commands will affect everything you write after you call. 

```swift
pdf.setContentAlignment(.Center) // .Left, .Center, .Right

pdf.setFont( UIFont ) // only affect pdf.addText(...) command
```

### Generate PDF data

```swift
let pdfData = pdf.generatePDFdata()

// write to file
try? pdfData.writeToFile(path, options: .DataWritingAtomic)

// or upload to Internet
// For example, Alamofire.upload(...)
```

## License
SimplePDF is available under the [MIT License](LICENSE).

## Authors
Nutchaphon Rewik

[![my twitter][1.1]][1]

[1.1]: https://img.shields.io/badge/Twitter-@nRewik-blue.svg?style=flat-square
[1]: https://www.twitter.com/nRewik