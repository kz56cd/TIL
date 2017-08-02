# [WIP] CLClocation 現在地取得

## overview


- 取得精度
	- 'CLLocationAccuracy'


- 許可
	- (iOS 8以降、)info.plistに位置情報の利用理由を記載しなければならない
	- NSLocationWhenInUseUsageDescription
	- 

### CLLocationManagerDelegate

didUpdateLocationsの引数locations

> （中略）Therefore, the most recent location update is at the end of the array.


## usage

```

class LocationService: NSObject {

	// initとかでセットする
    private func configureCLLocationManager() {
        locationManager.delegate = self
        locationManager.desiredAccuracy = kCLLocationAccuracyNearestTenMeters
        locationManager.distanceFilter = 5
        locationManager.requestWhenInUseAuthorization()
        startUpdatingLocation()
    }
    
    fileprivate func startUpdatingLocation() {
        locationManager.startUpdatingLocation()
    }
    
    fileprivate func stopUpdatingLocation() {
        locationManager.stopUpdatingLocation()
    }
}

// MARK - CLLocationManagerDelegate
extension LocationService: CLLocationManagerDelegate {

    func locationManager(_ manager: CLLocationManager, didUpdateLocations locations: [CLLocation]) {
        _ = locations.map {
            _currentLocation.value = CLLocationCoordinate2D(
                latitude: $0.coordinate.latitude,
                longitude: $0.coordinate.longitude
            )
        }
    }

    func locationManager(_ manager: CLLocationManager, didFailWithError error: Error) {
        locationManager.stopUpdatingLocation()
    }
    
    func locationManager(_ manager: CLLocationManager, didChangeAuthorization status: CLAuthorizationStatus) {
        switch status {
        case .notDetermined:
            stopUpdatingLocation()
        case .denied:
            stopUpdatingLocation()
        case .restricted:
            stopUpdatingLocation()
        case .authorizedAlways:
            startUpdatingLocation()
        case .authorizedWhenInUse:
            startUpdatingLocation()
        }
    }
}
```



## ref

- http://adragoona.hatenablog.com/entry/2014/05/12/215836
- https://gist.github.com/nantekkotai/2841743

