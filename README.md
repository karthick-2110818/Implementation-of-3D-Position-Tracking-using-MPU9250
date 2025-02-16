3D Position Tracking using MPU9250 IMU (Inertial Measurement Unit):
The MPU9250 is a popular 9-axis motion tracking device that integrates:
3-axis Gyroscope: Measures the rate of rotation (angular velocity) around the x, y, and z axes.
3-axis Accelerometer: Measures acceleration in three directions, useful for detecting linear movement and orientation.
3-axis Magnetometer: Measures magnetic fields along the x, y, and z axes, providing compass-like functionality and enhancing orientation sensing.
Key Features:
9 Degrees of Freedom (DoF): Combines data from the gyroscope, accelerometer, and magnetometer to provide precise orientation and motion tracking.
Digital Motion Processor (DMP): On-chip algorithms process sensor data for features like sensor fusion, which simplifies obtaining orientation (pitch, roll, yaw).
![image](https://github.com/user-attachments/assets/fe995a2d-018e-439b-8422-4bd9270df85b)

Implemenation of Codes:

The project implementation includes the use of Arduino, Python, and MATLAB for 3D position
tracking using the MPU9250 sensor, processing its accelerometer, gyroscope, and magnetometer
data to track motion and orientation in real-time. The integration of the three platforms allows for
precise data acquisition and processing as detailed below:
1. Arduino Code: The Arduino code is used to interface with the MPU9250 and collect motion data.
The code handles sensor calibration by applying offsets to the raw accelerometer data and then
prints out the adjusted accelerometer and gyroscope values in a comma-separated format. This
data is then passed to the serial port for further processing in Python.

![image](https://github.com/user-attachments/assets/afaeff0e-e748-4c4c-ae5e-efe99eb0fa25)


2. Python Code: The Python script reads real-time data from the serial port and stores it in a CSV
file. This data contains the readings from the MPU9250’s accelerometer and gyroscope, which
are used to track motion. By storing the data in a CSV file, it becomes easy to analyze and plot
the results in MATLAB. The Python code is designed to continuously collect data until the user
stops the script, providing flexibility in the duration of the data collection.
3. MATLAB Code: The MATLAB code processes the raw sensor data to estimate the object's
position in 3D space. Here's a breakdown of the code's functionalities:
o Data Import: The CSV file containing accelerometer and gyroscope data is read, and the
respective columns are extracted.
o Plotting: Separate plots for the accelerometer and gyroscope data are generated, allowing
for visual inspection of the data over time
o Sensor Fusion (AHRS Algorithm): The accelerometer and gyroscope data are processed
using the AHRS algorithm to compute the orientation of the object. The data is used to
compute the sensor’s rotation matrix, which helps translate sensor data to the Earth
frame.
o Tilt-Compensated Acceleration: The code calculates the tilt-compensated accelerometer
readings, which account for changes in orientation, making the acceleration data more
accurate.
o Linear Acceleration, Velocity, and Position: The tilt-compensated accelerometer data is
integrated to calculate linear velocity. After applying a high-pass filter to remove drift, the
velocity data is integrated once again to compute the linear position of the object in space.
o 3D Animation: A 3D animation is generated

![image](https://github.com/user-attachments/assets/d92c72cb-fc9f-4a85-b8c5-f899f78a1e2e)

![image](https://github.com/user-attachments/assets/e3f3c878-dcfe-463f-bdcf-d8f3d16c09f6)





