# Licensing

- [Licensing](#licensing)
  - [Description](#description)
  - [Assign license to the IE Hub](#assign-license-to-the-ie-hub)
  - [Identify which device has taken the license](#identify-which-device-has-taken-the-license)
  - [Check the license with TIA Portal](#check-the-license-with-tia-portal)

## Description

To work with a CPU 1517V , an access license is required. This chapter explains how to verify the license for the 1517V and how to assign it in the Industrial Edge Hub to your Industrial Edge Management.

## Assign license to the IE Hub

Before the assignment, you need to purchase the subscriptions of the application licenses at the [Edge Marketplace](https://www.dex.siemens.com/?selected=edge). To use the licenses for the application, at least one license should be allocated to the Industrial Edge Management (IEM) system that the target Industrial Edge Device belongs to. For this, manage the following steps:

1. Log into the [Industrial Edge Hub](https://umipomoh.iehub.eu1.edge.siemens.cloud/home)
2. Navigate to the Library.

 ![S7-1500V_Licensing_1](/docs/graphics/S7-1500V_Licensing_1.png)

3. Open the application “CPU 1517V”.

     ![S7-1500V_Licensing_2](/docs/graphics/S7-1500V_Licensing_2.png)

  Then, navigate to License management.

     ![S7-1500V_Licensing_3](/docs/graphics/S7-1500V_Licensing_3.png)

4. Select your subscription according to purchaser's e-mail and click on Manage.

![S7-1500V_Licensing_4](/docs/graphics/S7-1500V_Licensing_4.png)

5. Choose the target IEM instance according to its name and using button + assign the number of neeed licenses. Finally, click on Save.

![S7-1500V_Licensing_5](/docs/graphics/S7-1500V_Licensing_5.png)

 Please, note that license for one CPU1517V instance running on one Edge Device.

## Identify which device has taken the license

To identify which device has been assigned the license, click on "View list of granted device(s)".

![S7-1500V_Licensing_6](/docs/graphics/S7-1500V_Licensing_6.png)

Then, the list of devices with granted CPU1517V licenses is visualized and you can see the ID(s) of these devices:

![S7-1500V_Licensing_7](/docs/graphics/S7-1500V_Licensing_7.png)

When you open the app CPU1517V, the license status will show "License granted". If the device doesn't have a license, it will display "Not connected to backend service".

![Licensing_check_license_in_1517V](/docs/graphics/Licensing_check_license_in_1517V.png)

Now, you can search for the device associated with this device ID. To do this, log into your IEM, navigate to "Edge Devices," select one of your devices, and check the "Device ID" under "Additional Information" on the right side. Alternatively, the ID is visible also in URL.

![S7-1500V_Licensing_8](/docs/graphics/S7-1500V_Licensing_8.png)

When you open the 1517V-App, the license status will show "License granted". If the device doesn't have a license, it will display "Not connected to backend service".

![Download_TIA_project_7](/docs/graphics/Licensing_check_license_in_1517V.png)

## Check the license with TIA Portal

There are several ways to check the license of the CPU 1517V, such as using the webserver, API, Databus topic, or a system function in the PLC code. For more information, refer to the official documentation of the [1517V-PLC](https://support.industry.siemens.com/cs/document/109825448/s7-1500-virtual-controller-cpu-1517v(f)-function-manual?dti=0&lc=en-MW). In this chapter, we focus on implementing this using TIA Portal and reading the license information in the PLC. To do this, use this [SCL code](/src/GetLicenseInfo.scl) and paste it into a new function block (FB).

Once you have compiled and downloaded the project, you can monitor the FB. The image below shows whether the license is activated, the licensing state number, the remaining time to expiration during the grace period, and the licensing state.

![Licensing_TIA_License_granted](/docs/graphics/Licensing_TIA_License_granted.png)

