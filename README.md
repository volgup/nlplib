
# NLP Location Provider
Network Location Provider can use in POS device and smart android device sdk .


## Sopports Android 7 - 14 (Nougat-to-UPSIDE_DOWN_CAKE):
**Systems app tracking cases:**
**Network Location Provider is provided for you to:**
1. Will read data from cellular GNSS information  from App
2. and will calculate and parse  location information ,
3. view and analyze carrier phase (if it is present in the log file).

## Install the library
   implementation ('com.github.volgup:nlplib:1.0@aar') { transitive = true }

Or if the library is to be used only for debug builds and not release builds, then

    debugImplementation ('com.github.volgup:nlplib:1.0@aar') { transitive = true }

Add repository maven url, If required to find repositories version:

    repositories 
    {
        google()
        maven {
           url "https://github.com/volgup/nlplib/tree/main/releases/com/github/volgup/nlplib"
        }
    }

## Initialize start and stop location latlng's

**Start Nmea Location Service to capture Location using LocationListener:**

      NmeaLocationService.startLocService(getContext(),new LocationListener() 
    {
        @Override
        public void onLocationChanged(@NonNull Location location)
        { 
                                 
            Log.i("loc", "provider: " + location.getProvider() + "latlng: " + location.getLatitude() + "," + location.getLongitude() + " time: " + location.getTime());
    
        }
            
    }); 
**Stop location capturing:**

    NmeaLocationService.stopBackendService();

Last Recorded Location: (Required to start NmeaLocationService service
to get last Recorded location)

    NmeaLocationService.getLastRecLocation();

