```java
public class lab2{
    static lab_accel="",lab_ori="",lab_loc="";
    public static getSensorValue(){
        lab_accel.setText ( "Accelerometer:\n" +\
                    "X: " + AccelerometerSensor1.XAccel +\
                    "\nY: " + AccelerometerSensor1.YAccel +\
                    "\nZ: " + AccelerometerSensor1.ZAccel);
        lab_ori.setText ( "Orientation:\n" +\
                    "Roll: " + OrientationSensor1.Roll +\
                    "\nPitch: " + AccelerometerSensor1.Pitch +\
                    "\nAzimuth: " + AccelerometerSensor1.Azimuth);
        lab_loc.setText ( "Location:\n" +\
                    "[" + LocationSensor1.Latitude + "," + LocationSensor1.Longitude + "]");
    } 


    static float mylocLat=0,mylocLon=0;
    static float serverLat=0,serverLon=0;
    
    String temp="";

    public static btn_meClick(){
        mylocLat=LocationSensor1.Latitude;
        mylocLon=LocationSensor1.Longitude;
        lab_loc.setText ("My: " + Lat_M + ", " + Lon_M);
        HttpPost httpPost = new HttpPost(server_url) ;
        httpPost.setEntity(text=("lat="+Lat_M+"&lon="+Lon_M));
        lab_loc.setText = "My Location: " + responseContent;
        HttpResponse response = defaultHttpClient.execute (httpPost);
        ActivityStarter1.Action = "android.intent.action.VIEW";
        ActivityStarter1.DataUri = "geo:" + mylocLat + "," + mylocLon + "?z=zoom";
        ActivityStarter1.StartActivity();
    }

    public static btn_server.Click(){
        lab_loc.setText ("Server's Location: " + responseContent);
        HttpResponse response = defaultHttpClient.execute (httpPost);
        lab_info.setText (response);
        temp = split(responseContent, ",");
        serverLat = temp[0];
        serverLon = temp[1];
        ActivityStarter1.Action = "android.intent.action.VIEW"
        ActivityStarter1.DataUri = "geo:" + serverLat + "," + serverLon + "?z=zoom"
        ActivityStarter1.StartActivity()
    }

}


```