# Go Keychain

A library for accessing the Keychain for OSX and iOS.

Requires Mac OSX 9 or greater and iOS 7 or greater.

## Usage

```go
item := keychain.NewGenericPassword("MyService", "gabriel", []byte("toomanysecrets"), "com.mycorp", SynchronizableNo, AccessibleWhenUnlockedThisDeviceOnly)
err := keychain.AddItem(item)
if err == KeychainErrorDuplicateItem {
  // Duplicate
}

err := keychain.DeleteItem(item)
if err == KeychainErrorNotFound {
  // Not found
}

accounts, err := keychain.GetAccounts("MyService")
// Should have 1 account == "gabriel"
```
