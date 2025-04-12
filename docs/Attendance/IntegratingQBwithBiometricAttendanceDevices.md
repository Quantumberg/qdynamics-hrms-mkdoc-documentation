# Integrating Q-Dynamics HR with Biometric Attendance Devices

# Background

The Attendance punch logs from the biometric device are check-in and check-out logs of an employee. Q-Dynamics HR has a provision to store these logs in a document called Employee Checkin.

Attendance can then be marked based on the Employee Checkin records and the Shift Type of the employee by using Auto Attendance.

Hence, integrating your Biometric Device (or any access control system that collects IN/OUT logs), can be done using the following steps:

# 1. Setting up Auto Attendance to mark attendance from the Employee Checkin

Before you import/sync employees' Check-in and Check-out logs into your Q-Dynamics HR system, you will have to set up the employees and their shifts to be able to generate attendance using the Auto Attendance feature in Q-Dynamics HR.

Please refer to the following link to set up Auto Attendance: Set up Auto Attendance

Once you have set up the Employee master and assigned shifts to the employees, you are now ready to proceed to the next step.

# 2. Populating the Biometric Punch Logs into Q-Dynamics HR's Employee Checkin

Depending on your biometric system and its features, there can be a lot of ways you can populate the Punch logs into Q-Dynamics HR:

# 1. Use the Data Import Tool

* The simplest possible solution (in terms of implementation complexity) would be to generate an Excel/CSV of the Check-in/Check-out logs and use the built-in Data Import Tool in Q-Dynamics HR to periodically import the logs to your Employee Checkin document.

* Please refer to the documentation on the Data Import Tool for more on how to do this.

# 2. API Integration

You can automate the process of syncing the Biometric Punch Logs by integrating it with the available API in Q-Dynamics HR.

This method requires some technical knowledge, and you should probably get in touch with your Q-Dynamics HR implementor or Biometric system vendor.

Steps:

1. You will first need to create a user in your Q-Dynamics HR instance that will be used for creating logs, since this API method requires login. Make sure this user has all the required permissions to create Employee Checkin records.

2. Generate the API Key and API Secret for the user, which will be used for authentication.

3. Ensure that the Attendance Device ID (Biometric/RF tag ID) is set correctly for each employee in the system, based on your biometric device.

4. The API implementation details can be found here, and the API can be accessed at:
`/api/method/hrms.hr.doctype.employee_checkin.employee_checkin.add_log_based_on_employee_field.`

5. You can write a script to send a POST request to this API This endpoint finds the relevant employee using the employee field value and creates an Employee Checkin record. 

API Endpoint Details:


* URL: 
`/api/method/hrms.hr.doctype.employee_checkin.employee_checkin.add_log_based_on_employee_field`

* Method: POST

* Params:

    * **employee_field_value:** The value to look for in the employee field. This will be the Attendance Device ID found in your biometric logs and also set in the employee record.

    * **timestamp:** The timestamp of the log. Format (string): '2022-04-08 10:48:08.000000'

    * **device_id (optional):** Location / Device ID. A short string.

    * **log_type (optional):** Direction of the punch if available (IN/OUT).

    * **skip_auto_attendance (optional):** Whether to skip auto attendance for this log (0 or 1).

    * **employee_fieldname (default: attendance_device_id):** Name of the field in the Employee DocType used for lookup.

* Response: Returns the created Employee Checkin document object.


