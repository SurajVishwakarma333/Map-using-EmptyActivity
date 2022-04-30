# Map-using-Empty-Activity-
Android application which shows my specified Location. In this i used Empty Activity.

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
