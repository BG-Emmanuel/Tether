# Tether - The Proactive Luggage Intelligence System

## 1. Description

Tether is a hybrid IoT and mobile software solution designed to transform passive luggage tracking into active security and telemetry intelligence. By integrating a custom multi-sensor hardware module with a cross-platform mobile application, Tether provides users with real-time awareness of their bag's location, physical condition, and security status—independent of crowded Bluetooth networks.

## 2. Problem Statement

Current tracking devices (like AirTags) rely on passive crowdsourcing, offering delayed location updates and zero insight into the bag's physical state. Travelers face anxiety over lost luggage, have no proof of mishandling for insurance claims, and cannot detect theft or tampering until it is too late.

## 3. Objectives

- To provide real-time GPS location of luggage globally without relying on nearby third-party devices.
- To detect and log physical impacts (shocks), orientation changes, and altitude shifts to reconstruct the bag's journey.
- To implement proactive security alerts for unauthorized movement, opening (light exposure), or separation from the owner.
- To create a "Digital Tape" timeline that visualizes the bag's condition and location history for user transparency and insurance claims.

## 4. Target Audience

- Frequent flyers and business travelers.
- Outdoor enthusiasts with expensive gear.
- Elderly individuals prone to forgetting belongings.
- Logistics companies requiring high-value asset monitoring.

## 5. Core Technologies & Stack

- **Hardware:** Custom PCB with ESP32/SAMD51 MCU, Quectel LTE-M module, GPS, 6-Axis Accelerometer, Ambient Light Sensor, Barometer, and 2500mAh Li-Po battery.
- **Firmware:** C/C++ (Arduino/FreeRTOS) for sensor fusion and low-power management.
- **Backend:** AWS IoT Core for device management, DynamoDB for telemetry storage, and Lambda functions for alert rule processing.
- **Mobile App:** React Native (Expo) for cross-platform compatibility, integrating Mapbox for real-time tracking visualization.

## 6. Key Features (MVP)

1. **Live Tracking:** View luggage location on a map with cellular/GPS updates every 60 seconds during motion.
2. **Shock & Tamper Alerts:** Instant push notification if the bag experiences a high-G impact or if the light sensor detects the bag being opened.
3. **Flight Sync Integration:** Automatically detects altitude changes to confirm the bag has been loaded onto the aircraft.
4. **Proximity Fence:** Alerts user if they move more than 50 meters away from their stationary bag.
5. **Journey Replay:** A playback feature showing the bag's route and logged sensor events on a timeline.

## 7. Scope & Constraints

- **Scope:** Design of a functional hardware prototype, firmware development, backend architecture, and a user-friendly mobile application.
- **Constraints:** Battery life optimization (target 5-7 days with mixed usage), global cellular roaming agreements, and compliance with airline battery safety regulations (under 100Wh).