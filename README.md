# PPIT_database

## File content
The folder name is the date when these data were collected. 

### Data file (Pickle)

  Each folder has a number of pickle files in it. 
  Each pickle file are named in the following order: Date_IndividualID_set_SetNumber_Repetition.p.
  In each pickle file, it contains a dictionary as follows
  ```
  pressure: The pressure sensor data, shape of (frame_num, 6, 12)
  location: The location sensor data, shape of (frame_num, 7, 24)
  pressure map: The pressure map data matrix, shape of (frame_num, 13, 36)
  keypoint: the 3D joint coordinates data matrix, shape of (frame_num, joint_num, xyz)
  ```

The pressure sensor data and location senesor data are raw sensor value from the smart mat hardware. 
The pressure sensor distribution looks like the figure below. Each grey pad is the sensor coverage area. There are 72 sensors which are arranged in the shape of (6, 12)

<img width="600" alt="image" src="https://github.com/tg0uk/PPIT_database/assets/153914917/5a94fb4c-e31b-4d3c-a8a5-a969b629ed50">

The location sensor distribution looks like the figure below. Each grey pad is the sensor coverage area. There are 168 sensors which are arranged in the shape of (7, 24)

<img width="600" alt="image" src="https://github.com/tg0uk/PPIT_database/assets/153914917/cef99a7b-0e45-41d8-9719-64d7d7233cc5">

The location sensor and pressure sensor area are the same with location sensor overlapping on top of the pressure sensors.

The pressure map data are calculated from pressure sensor data and location sensor data. It has the same coverage as pressure sensor and location sensor. The only difference is the pressure grid resolution which has a shape of (13, 36). 

<img width="600" alt="image" src="https://github.com/tg0uk/PPIT_database/assets/153914917/fbb006da-79f5-4578-ab15-17844eae9c5b">



### Log file (YAML)


  The log file described some details of the data file.
  ```
- joints: The position of data for each joint. For example, "Left ankel" has position of 12. The corresponding coordinates data in the pickle file should be **keypoint[:,11,:]**. It returns a 2D matrix of row as frames and col as the xyz coordinates
- frequency: The frequency of data frame in Hz. For example, the frequency of 10 means the time gap between each time frame is 100 millisecond.
- axis_range: The value of coordinate ranges from -32767 to 32767
- data_folder_list: The log describe these data folder
```

  
