

This sample is based on the ESPRESSIF ESP32 sample from https://github.com/azure-samples/iot-middleware-freertos-samples

To use this sample with Device Provisioning Service (DPS) and x509 certificates, follow these steps:

1. Generate and update the certificates in DPS
    > Example of guideline to generate certificates: https://learn.microsoft.com/en-us/azure/iot-hub/tutorial-x509-openssl
2. Create an individual enrollment in your DPS, using x509 authentication and the device certificate generated in step 1
3. Set the kconfig configuration in this sample
    > Run `idp.py menuconfig` (similar to instructions in the base [ESP32](https://github.com/Azure-Samples/iot-middleware-freertos-samples/tree/main/demos/projects/ESPRESSIF/esp32#update-sample-configuration) sample)

    > Disable `Use PnP in Azure Sample`

    > Enter your `device id` (from DPS individual enrollment) into `Azure IoT Device ID`

    > Select `X509 Certificates` in `Azure IoT Authentication Method`

    > Enter your device certificate (see instructions in the base [ESP32](https://github.com/Azure-Samples/iot-middleware-freertos-samples/tree/main/demos/projects/ESPRESSIF/esp32#update-sample-configuration) sample)

    > Enter your device private key (see instructions in the base [ESP32](https://github.com/Azure-Samples/iot-middleware-freertos-samples/tree/main/demos/projects/ESPRESSIF/esp32#update-sample-configuration) sample)

    > Enable `Enable Device Provisioning Sample`

    > Enter your DPS ID Scope

    > Enter your DPS individual enrollment device ID into `Azure Device Provisioning Service Registration ID`

4. Follow [remaining steps](https://github.com/Azure-Samples/iot-middleware-freertos-samples/tree/main/demos/projects/ESPRESSIF/esp32#build-the-image) in the base ESP32 sample to build, flash and monitor.
