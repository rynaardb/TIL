# Attributed String

Usefull and frequenlty used attributed string related tasks

## HTML
```swift
// For HTML you need to make sure you are on the main thread
private static func attributedHtml(_ string: String?) -> NSAttributedString? {
        guard let message = message else { return nil }

        if let htmlAttributedString = try? NSMutableAttributedString(data: Data(string.utf8),
                                  options: [.documentType: NSAttributedString.DocumentType.html],
                                  documentAttributes: nil) {
            let range = NSRange(location: 0, length: htmlAttributedString.string.count)

            htmlAttributedString.addAttribute(.foregroundColor, value: Theme.textColorSecondary, range: range)
            htmlAttributedString.addAttribute(.font, value: UIFont(.semibold, 17), range: range)

            return htmlAttributedString
        } else {
            return nil
        }
    }
```
