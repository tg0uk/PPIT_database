# PPIT_database

## File content
The folder name is the date when these data were collected. 

### Data file (Pickle)
  Each folder has a number of pickle files in it. 
  Each pickle file are named in the following order: Date_IndividualID_set_SetNumber_Repetition.p.
  In each pickle file, it contains a dictionary as follows
  ```
  pressure: The pressure sensor data, shape of 
  location: The location sensor data
  pressure map: The pressure map data matrix, shape of [frame_num, row_num, col_num]
  keypoint: the 3D joint coordinates data matrix, shape of [frame_num, joint_num, xyz]
  ```
### Log file (YAML)
  The log file described some details of the data file.
  ```
joints: The position of data for each joint. For example, "Left ankel" has position of 12. The corresponding coordinates data in the pickle file should be **keypoint[:,11,:]**. It returns a 2D matrix of row as frames and col as the xyz coordinates
frequency: The frequency of data frame in Hz. For example, the frequency of 10 means the time gap between each time frame is 100 millisecond.
axis_range: The value of coordinate ranges from -32767 to 32767
```

  
