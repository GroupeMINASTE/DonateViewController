# DonateViewController

[![License](https://img.shields.io/github/license/GroupeMINASTE/DonateViewController)](LICENSE)
[![Issues](https://img.shields.io/github/issues/GroupeMINASTE/DonateViewController)]()
[![Pull Requests](https://img.shields.io/github/issues-pr/GroupeMINASTE/DonateViewController)]()
[![Code Size](https://img.shields.io/github/languages/code-size/GroupeMINASTE/DonateViewController)]()
[![CodeFactor](https://www.codefactor.io/repository/github/groupeminaste/donateviewcontroller/badge)](https://www.codefactor.io/repository/github/groupeminaste/donateviewcontroller)
[![Open Source Helpers](https://www.codetriage.com/groupeminaste/donateviewcontroller/badges/users.svg)](https://www.codetriage.com/groupeminaste/donateviewcontroller)

A view controller to make donations.

## Installation

Add `https://github.com/GroupeMINASTE/DonateViewController.git` to your Swift Package configuration (or using the Xcode menu: `File` > `Swift Packages` > `Add Package Dependency`)

## Usage

> ⚠️ You need to register your in app purchases in App Store Connect to make it work. The name and the price of purchases will be used.

First, import the package in your view controller where you want to open the DonateViewController.

```swift
// Import the package
import DonateViewController
```

Create a method to open it:

```swift
func openDonateViewController() {
    // Create the view controller
    let controller = DonateViewController()
    
    // Customize view title, header and footer (optional)
    controller.title = "Donate"
    controller.header = "Select an amount to donate:"
    controller.footer = "The donations help us to improve our projects (...)"
    
    // Add donations
    controller.add(identifier: "my.app.identifier.mydonation1")
    controller.add(identifier: "my.app.identifier.mydonation2")
    // ... (add as many donations as you want)
    
    // And open your view controller: (two ways)
    
    // 1. In your navigation controller
    navigationController?.pushViewController(controller, animated: true)
    
    // 2. In a modal
    present(UINavigationController(rootViewController: controller), animated: true, completion: nil)
}
```

And call this method when you want to open the DonateViewController:

```swift
openDonateViewController()
```

## Customize colors for theming (iOS < 13)

Before iOS 13, no dark theme was implemented in controllers. If you want to implement your custom dark theme, create an extension or subclass DonateViewController to change the colors of the view controller. (background, ...)

## Donate to the developer

Feel free to make a donation to help the developer to make more great content! [Donate now](https://paypal.me/NathanFallet)
