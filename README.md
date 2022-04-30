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
              
       
       
     3. In .java file
     
     
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
               
               
               
               
               
               
               
               
     3. In .xml file 
      
      
      
      
      
      
      
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
         

              
             
              
              













NOTES :-
   
  To add different types of google maps.
  
  
  
        map.setMapType(GoogleMap.MAP_TYPE_HYBRID);
        map.setMapType(GoogleMap.MAP_TYPE_SATELLITE);
        map.setMapType(GoogleMap.MAP_TYPE_NORMAL);
        map.setMapType(GoogleMap.MAP_TYPE_NONE);
        map.setMapType(GoogleMap.MAP_TYPE_TERRAIN);
        
        
   to add marker.      
   
   
   
        map.addMarker(new MarkerOptions().position(Mumbai).title("Marker in India"));
        
   to move camera to the marker.     
   
   
   
   
        map.moveCamera(CameraUpdateFactory.newLatLng(Mumbai));
        
        
        
   to add traffic line.    
   
   
   
   
        map.setTrafficEnabled(true);
        
        
        
        
        
        
        
        
        
        
        
        
        

        
