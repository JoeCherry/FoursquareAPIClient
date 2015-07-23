# FoursquareAPIClient

Very Simple Swift wrapper for Foursquare API v2

![Demo](./screen.png)

## Installation

Copy all the files from the FoursquareAPIClient folder to your project.

## Usage

### Setup session

```swift
let client = FoursquareAPIClient(accessToken: “YOUR_ACCESS_TOKEN”)
```
or

```swift
// Set v=YYYYMMDD param
let client = FoursquareAPIClient(accessToken: “YOUR_ACCESS_TOKEN”, version: "20140723")
```

### Search Venues

```swift
let parameter: [String: String] = [
    "ll": "35.702069,139.7753269",
    "limit": "10",
];

client.requestWithPath("venues/search", parameter: parameter) {
    (data, error) in

    // parse the JSON with NSJSONSerialization or Lib like SwiftyJson

    // result: {"meta":{"code":200},"notifications":[{"...
    println(NSString(data: data!, encoding: NSUTF8StringEncoding))
}
```

## Requirements

Swift 1.2 / iOS 8.0+


===========
koogawa, July 2015.