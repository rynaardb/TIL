# Core Data

## NSPersistentContainer

Provides two managed object contexts by default: 

`viewContext` a context to execute on the main thread

a background context to execute long running queries

```swift
persistentContainer.performBackgroundTask { moc in
    // execute long running queries in the background            
}
```

## Fetching

* NSFetchRequest
* NSPredicate
* NSManagedObjectContext

```swift
let fetchRequest = NSFetchRequest<Person>(entityName: "Person")

// optional predicate to filter fetched data
//fetchRequest.predicate = NSPredicate(format: "id == %@", "4FDB2C1D-03E2-4A1D-91C5-A911A9E5E697")

do {
    try context.fetch(fetchRequest)
} catch {
    fatalError("Failed to fetch data: \(error)")
}
```

## Inserting

* NSManagedObjectContext

```swift
do {
    let person = Person(context: context)
    person.id = id
    person.name = name

    try context.save()
} catch {
    fatalError("Failed to insert data: \(error)")
}
```

## Deleting

* NSManagedObjectContext

```swift
do {
     context.delete(person)

     try context.save()
} catch {
    fatalError("Failed to delete data: \(error)")
}
```

## NSFetchedResultsController

TODO

## Predicates to fetch between two dates

```swift
let calendar = Calendar.current
let fromDate = calendar.startOfDay(for: Date())
let toDate = calendar.date(byAdding: .day, value: 1, to: dateFrom)

let fromPredicate = NSPredicate(format: "%@ >= %@", fromDate as NSDate, fromDate as NSDate)
let toPredicate = NSPredicate(format: "%@ < %@", toDate as NSDate, toDate as NSDate)
let datePredicate = NSCompoundPredicate(andPredicateWithSubpredicates: [fromPredicate, toPredicate])
```