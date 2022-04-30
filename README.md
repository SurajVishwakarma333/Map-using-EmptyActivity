# Map-using-Empty-Activity-
Android application which shows my specified Location. For creating project i used Empty Activity.


STEPS TO CREATE MAP IN EMPTY ACTIVITY :-

1. add dependency in build.gradle(app level)
    
    
    
              implementation 'com.google.android.gms:play-services-maps:18.0.2'
              
              
              
              
2. add permissions and give API_KEY in Manifest.xml 
    
    
    
              <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
              <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
              <uses-permission android:name="android.permission.INTERNET" />
              
              <meta-data
              android:name="com.google.android.geo.API_KEY"
              android:value="AIzaSyDk_vJQDTKJnyQIAzAO-HhUk1_TF-_aQ6c" />
              
       
       
3. .java file
     
     
               package com.example.map;

               import androidx.annotation.NonNull;
               import androidx.appcompat.app.AppCompatActivity;
               import androidx.fragment.app.FragmentActivity;

               import android.os.Bundle;

               import com.google.android.gms.maps.CameraUpdateFactory;
               import com.google.android.gms.maps.GoogleMap;
               import com.google.android.gms.maps.OnMapReadyCallback;
               import com.google.android.gms.maps.SupportMapFragment;
               import com.google.android.gms.maps.model.LatLng;
               import com.google.android.gms.maps.model.MarkerOptions;;
     
               public class MainActivity extends FragmentActivity implements OnMapReadyCallback {

               GoogleMap map;

               @Override
               protected void onCreate(Bundle savedInstanceState) {
               super.onCreate(savedInstanceState);
               setContentView(R.layout.activity_main);

               SupportMapFragment mapFragment = (SupportMapFragment) getSupportFragmentManager().findFragmentById(R.id.map);
               mapFragment.getMapAsync(this);
               }

               @Override
               public void onMapReady(@NonNull GoogleMap googleMap) {
               LatLng Mumbai = new LatLng(19.17, 72.83);
               map=googleMap;

               map.addMarker(new MarkerOptions().position(Mumbai).title("Marker in India"));
               map.moveCamera(CameraUpdateFactory.newLatLng(Mumbai));
               }
               }
               
               
               
               
               
               
               
               
4. .xml file 
      
      
      
      
      
      
      
               <?xml version="1.0" encoding="utf-8"?>
               <androidx.constraintlayout.widget.ConstraintLayout
               xmlns:android="http://schemas.android.com/apk/res/android"
               xmlns:app="http://schemas.android.com/apk/res-auto"
               xmlns:tools="http://schemas.android.com/tools"
               android:layout_width="match_parent"
               android:layout_height="match_parent"
               tools:context=".MainActivity">  
               
               <fragment
               android:id="@+id/map"
               android:name="com.google.android.gms.maps.SupportMapFragment"
               android:layout_width="match_parent"
               android:layout_height="match_parent"
               app:layout_constraintTop_toBottomOf="@+id/frgment" />
               
               </androidx.constraintlayout.widget.ConstraintLayout>
         

              
             
              
              











![map](https://user-images.githubusercontent.com/101108540/166101048-f3610f75-ca08-4edd-9df3-96ef0cc070a7.jpeg)

NOTES :-
   
  To add different types of google maps.
  
  
  
        map.setMapType(GoogleMap.MAP_TYPE_HYBRID);
        map.setMapType(GoogleMap.MAP_TYPE_SATELLITE);
        map.setMapType(GoogleMap.MAP_TYPE_NORMAL);
        map.setMapType(GoogleMap.MAP_TYPE_NONE);
        map.setMapType(GoogleMap.MAP_TYPE_TERRAIN);
        
        
   to add marker.      
   
   
   
        map.addMarker(new MarkerOptions().position(Mumbai).title("Marker in India"));
        
   Move the camera to the map marker and zoom in closer.     
   
   
   
   
        map.moveCamera(CameraUpdateFactory.newLatLng(Mumbai));
        map.moveCamera(CameraUpdateFactory.zoomTo(15)); 
        
        
   to add traffic line.    
   
   
   
   
        map.setTrafficEnabled(true);
        
        
        
   when viewed close up, will have 3D buildings visible
   
   
        
        
   
        
        GoogleMap.setBuildingsEnabled(true)
        
        
        
        
        
  Changing zoom level and setting minimum/maximum zoom      
        
        
        
        map.setMinZoomPreference(6.0f);
        map.setMaxZoomPreference(14.0f);
        CameraUpdateFactory.zoomIn();
        CameraUpdateFactory.zoomOut();
        CameraUpdateFactory.zoomTo(float);
        CameraUpdateFactory.zoomBy(float); 
        CameraUpdateFactory.zoomBy(float, Point);
        
        
        
        
        
  Move the camera instantly to India with a zoom of 15.
  
  
  
  

  
  
        map.moveCamera(CameraUpdateFactory.newLatLngZoom(sydney, 15));
        
        
      
      
      
        
  Zoom in, animating the camera.     
        
        
        
        
        
        
        
        map.animateCamera(CameraUpdateFactory.zoomIn());
        
        
        
        
        
  Zoom out to zoom level 10, animating with a duration of 2 seconds.      
        
        
        
        
        
        
        map.animateCamera(CameraUpdateFactory.zoomTo(10), 2000, null);
        
        
        
  
  for compass on map
  
  
  
        mUiSettings.setCompassEnabled(true);
        mUiSettings.setCompassEnabled(false);
        
        
        
  for zoomin/zoomout button +/- button on map      


        package com.example.chaseapppractice;
        
        import android.os.Bundle;

        public class MainActivity extends FragmentActivity implements OnMapReadyCallback {
        
        private UiSettings mUiSettings;
        
         @Override
        protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);
        }
        Override
        public void onMapReady(@NonNull GoogleMap googleMap) {
        LatLng Mumbai = new LatLng(19.17, 72.83);
        map=googleMap;

        map.addMarker(new MarkerOptions().position(Mumbai).title("Marker in India"));
        map.moveCamera(CameraUpdateFactory.newLatLng(Mumbai));
        
        mUiSettings = map.getUiSettings();
        mUiSettings.setZoomControlsEnabled(true);
        
              }
        }
  
        
        
        
        
        
        
        


        
