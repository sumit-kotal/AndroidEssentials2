# AndroidEssentials2

- Create a UI with only a button and Textview.
- Initialize the button and textview
- Add a LocationManager and LocationListener Object
- Initialize LocationManager to :
	locationManager = (LocationManager) getSystemService(LOCATION_SERVICE);
- Now add the Listener and override all methods in it
- Create a method to handle the button click event and add the Following Code:
	
	locationManager.requestLocationUpdates(LocationManager.NETWORK_PROVIDER,5000,0, locationListener);
	
  >1st parameter - provider (Can be GPS or Network) - GPS is slower as compared to network
  >2nd parameter - minTime (Time for refreshing the location in milliseconds)
  >3rd parameter - minDistance (Minimum distance after which location is updated) - If 0 is given then location is updated according to time
  >4th parameter - locationListener (The listener for location)
  
- ACCESS_FINE_LOCATION and ACCESS_COARSE_LOCATION is to be declared in manifest
- In onLocationChanged update UI changes like adding Latitude and Longitude to textview using: 
 location.getLatitude() and location.getLongitude()
- In the onProviderDisabled add intent to go to enable gps when it is off as follows:
	Intent it = new Intent(Settings.ACTION_LOCATION_SOURCE_SETTINGS);
                startActivity(it);
- Now just add the button click method in the onCreate and run the app.
