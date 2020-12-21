# Wind-Turbine-Anaylsis
Monitor wind energy production

## Table of Content
* [Objective](#objective)
* [Data](#data)
* [Process](#process)
* [Control Chart Annual analysis](#control-chart-annual-analysis)
* [Control Chart Monthly analysis](#control-chart-monthly-analysis)

## Objective
* Monitor wind energy production
* Detect any changes in the generation of power and notify the system of any out of control instances

## Data
* Used SCADA dataset on a wind turbine in Turkey from [Kaggle](https://www.kaggle.com/berkerisen/wind-turbine-scada-dataset).
* Data consist of 4 features:
	* Date/Time 
	* LV ActivePower (kW)
	* Wind Speed (m/s) 
	* TheoreticalPowerCurve (KWh)
	* Wind Direction (°)

## Process
* Importing data and libraries.
* Plotting Data Distribution Charts.
* Getting Data correlation with respect to the Cumulative Variance.
* Data cleaning and removing.
* Data aggregation based on months for Annual Anaylsis
* Data aggregation based on days for Monthly Anaylsis
* Calcualte the control limits - CL(Centre Line), UCL(Upper Centre Line), LCL(Lower Centre Line):
	* Annual Anaylsis: There will be one chart for whole year as shown below
	![Annual Chart](https://github.com/paliwalabhishek/Wind-Turbine-Anaylsis/images/annualChart.jpg)
	* Monthly Anaylsis: There will be 12 charts for each month as shown below
	![Monthly Out of Control Chart](https://github.com/paliwalabhishek/Wind-Turbine-Anaylsis/images/monthlyOutOfControl.JPG)
* Validation - to find Out of control points
* Correcting or solving the Out of control situations 

## Control Chart Annual analysis
* All the sample points are within the upper and lower control limits of both the types of charts.
* Studying these charts conculsion can be drwan that the system is in control .
* Hence, the active power produced is within the limits of the tolerance considered for the theoretical production of this power.
* This change in the results is due to the fact that I considered the mean of data for the entire month instead of considering each day separately. Because of this the system ignores the exact day and time it is out of control.

## Control Chart Monthly analysis
*	The sample points are out of the upper limit of theoretical output for the month of June and September.
*	At one instance the sample is out of the lower limit of the theoretical output for the month of August.
*	This means that in June and September there came a point where the system produced a bit more power than the expected output.
*	According to study in wind energy the problems that might have caused this change might be :
	*	The wind speed changed as compared to the mean speed of the previous day.
	*	Also the wind direction changed by a large amount of degrees.
	*	The oil in the gearbox might be heating up or the engineers need to check the gearbox vibrations that may cause unnecessary noise (disturbance), this could signal that a failure is about to happen. 
	*	The change in data can be due to the actual change in the characteristics that produces wind or it might just be a reading errors like Rotor speed reading error (RSRE), Temperature measurement module failure error (TMFE) etc.
*	After eliminating the out of control points for all the 3 months, system  become in control as shown below
		![Monthly In control Chart](https://github.com/paliwalabhishek/Wind-Turbine-Anaylsis/images/monthlyInOfControl.JPG)
*	That is the system finally produces the expected amount of power it is supposed to without any surges or any dips in the production.


	



