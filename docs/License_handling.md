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
2. Navigate to the Library

 ![S7-1500V_Licensing_1](/docs/graphics/S7-1500V_Licensing_1.png)

3. Open the application “CPU 1517V”

     ![S7-1500V_Licensing_2](/docs/graphics/S7-1500V_Licensing_2.png)

    Here, you can view the number of licenses purchased, available, and in use.

4. Select the entitlement “run-plc” from the dropdown menu to display the used licenses
5. Choose the target IEM instance
6. Click on ”Manage Subscriptions”
7. In the “Actions” column, click “+” to allocate subscriptions

    ![Licensing_allocate_subscription](/docs/graphics/Licensing_allocate_subscription.png)

    In the next window, the licenses can be allocated.

    ![Licensing_allocate_subscription_2](/docs/graphics/Licensing_allocate_subscription_2.png)

## Identify which device has taken the license

To identify which device has been assigned the license, click on "See Granted 1 Device(s)" as shown in the allocation image. A window will open displaying the device ID.

![Licensing_Granted_ED](/docs/graphics/Licensing_Granted_ED.png)

Now, you can search for the device associated with this device ID. To do this, log into your IEM, navigate to "Edge Devices," select one of your devices, and check the "Edge Device ID" under "Additional Information" on the right side.

![Licensing_check_device_ID_in_IEM](/docs/graphics/Licensing_check_device_ID_in_IEM.png)

If you have many devices and don't want to manually search for the ID in each one, you can add your device ID to the URL in your "Edge Device"-screen. For example: https://iem.demo.siemens.com/iem-ui/#/devices/a3391c0ca878468e93fb0aba79ecd8ac.

![Licensing_add_ID_in_URL](/docs/graphics/Licensing_add_ID_in_URL.png)

When you open the 1517V-App, the license status will show "License granted". If the device doesn't have a license, it will display "Not connected to backend service".

![Download_TIA_project_7](/docs/graphics/Licensing_check_license_in_1517V.png)

## Check the license with TIA Portal

There are several ways to check the license of the CPU 1517V, such as using the webserver, API, Databus topic, or a system function in the PLC code. For more information, refer to the official documentation of the [1517V-PLC](https://support.industry.siemens.com/cs/document/109825448/s7-1500-virtual-controller-cpu-1517v(f)-function-manual?dti=0&lc=en-MW). In this chapter, we focus on implementing this using TIA Portal and reading the license information in the PLC. To do this, use this [SCL code](/src/GetLicenseInfo.scl) and paste it into a new function block (FB).

Once you have compiled and downloaded the project, you can monitor the FB. The image below shows whether the license is activated, the licensing state number, the remaining time to expiration during the grace period, and the licensing state.

![Licensing_TIA_License_granted](/docs/graphics/Licensing_TIA_License_granted.png)

