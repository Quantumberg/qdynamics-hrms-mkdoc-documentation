# Auto Attendance

Auto Attendance marks attendance for employees assigned to a shift based on the records in the Employee Checkin document and the Auto Attendance Settings of that shift.

    Note: Shift Type needs to be set up and assigned to employees before creating 'Employee Checkin' records. 
    Attendance will be marked by Auto Attendance only for check-in records that are created after setting up and 
    assigning an employee to their shift type. 

# Steps to Set Up Auto Attendance

You can configure Auto Attendance by following these steps:

# 1. Define Shift Type with Auto Attendance Enabled

Create a Shift Type and enable the Auto Attendance option in its settings.

Go to:

    Home > Human Resources > Attendance > Shift Type

* Enable the Auto Attendance checkbox.

* Configure the shift timings, grace periods, and working hour calculations as required.

# 2. Assign these shifts to employees 

Once you have set up a shift, you will have to assign this shift to the employees. You can assign this to an employee using one of the two methods given below:

*  Method 1: Using the Shift Assignment Document

Assign shifts to employees on a date-to-date basis.

Navigate to:

    Home > Human Resources > Attendance > Shift Assignment

Select the employee and assign the shift for specific dates.

* Method 2: Setting a Default Shift in the Employee Master

To assign a permanent shift that applies every day:

Go to:

    Home > Human Resources > Employee

Open the employee record.

Under Attendance and Leave Details, set the Default Shift.

    Note: If both a Shift Assignment and a Default Shift are configured for an employee, 
    the system will prioritize the Shift Assignment.

# 3. Setup Attendance Device ID in Employee

Biometric systems often assign a unique device ID to each employee. To ensure that Employee Check-in records sync correctly with Q-Dynamics HR, you must map each biometric ID to the corresponding employee in the system.

To do this, set the following field in the Employee master:

    Employee > Attendance and Leave Details > Attendance Device ID (Biometric/RF tag ID)

This links the biometric logs with the right employee profile during attendance processing.

# 4. Import or Sync Employee Check-ins

# 4. Import or Sync Employee Check-ins

Once you are done with the above steps you can import/sync the Employee Checkin and start generating attendance automatically.

Please refer to this article to know more about populating Employee Checkins from an external system: Integrating Q-Dynamics HR with Biometric Attendance Devices