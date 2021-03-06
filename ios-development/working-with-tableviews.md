# Working with Table Views

## An easy way to deal with reusable UITableView Cells

```swift
protocol ReusableView {
    static var reuseIdentifier: String { get }
}
```

```swift
extension ReusableView {
    static var reuseIdentifier: String {
        return String(describing: self)
    }
}
```

```swift
extension UITableViewCell : ReusableView { }
```

```swift
extension UITableView {
    func dequeue<T : UITableViewCell>(for indexPath: IndexPath) -> T {
        let cell = dequeueReusableCell(withIdentifier: T.reuseIdentifier, for: indexPath)
        return cell as! T
    }
}
```

```swift
class SearchViewController: UITableViewController {
    override func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
        // Instead of this
        // let cell = tableView.dequeueReusableCell(withIdentifier: "reuseIdentifier", for: indexPath)

            // We can write this
        let cell: SearchResultCell = tableView.dequeueReusableCell(for: indexPath)

        return cell
    }
}
```

## Swipe actions

```swift
func tableView(_ tableView: UITableView, canEditRowAt indexPath: IndexPath) -> Bool {
    return true
}
    
func tableView(_ tableView: UITableView, editActionsForRowAt indexPath: IndexPath) -> [UITableViewRowAction]? {
    let deleteAction = UITableViewRowAction(style: .destructive, title: "Delete") { _, _ in
        // Delete action here
    }
    deleteAction.backgroundColor = .red
    return [deleteAction]
}
```