# Plugging Devices into Power Outlets

You are developing an application that helps users manage and control various electronic devices by plugging them into power outlets. Each device has different plug types, voltage, and amperage requirements. To ensure compatibility and safety, you need to create adapters for different devices to allow them to be plugged into standard power outlets.

## Adaptee Objects:

- Laptop - Represents a laptop device that needs to be plugged into a power source. It has the charge() method.

- Refrigerator - Represents a refrigerator device that requires a power source. It has the startCooling() method.

- SmartphoneCharger - Represents a smartphone charger that needs to be plugged in for charging. It has the chargePhone() method.

## Target Object:

- PowerOutlet - Represents a standard power outlet with a common interface for plugging in devices. It defines the plugIn() method as the target method.

## Adapter Objects:

- LaptopAdapter - An adapter for plugging a laptop into a standard power outlet. It adapts the Laptop to the PowerOutlet interface, translating plugIn() to charge().

- RefrigeratorAdapter - An adapter for plugging a refrigerator into a standard power outlet. It adapts the Refrigerator to the PowerOutlet interface, translating plugIn() to startCooling().

- SmartphoneAdapter - An adapter for plugging a smartphone charger into a standard power outlet. It adapts the SmartphoneCharger to the PowerOutlet interface, translating plugIn() to chargePhone().

## UML DIAGRAM

---
title: UML class diagram
---
classDiagram
    direction TB

    class PowerOutlet {
        <<interface>>
        +plugIn() void
    }

    class LaptopAdapter {
        -laptop Laptop
        +LaptopAdapter(laptop Laptop)
        +plugIn() void
    }

    class RefrigeratorAdapter {
        -refrigerator Refrigerator
        +RefrigeratorAdapter(refrigerator Refrigerator)
        +plugIn() void
    }

    class SmartphoneAdapter {
        -smartphoneCharger SmartphoneCharger
        +SmartphoneAdapter(smartphoneCharger SmartphoneCharger)
        +plugIn() void
    }

    class Laptop {
        +charge() void
    }

    class Refrigerator {
        +startCooling() void
    }

    class SmartphoneCharger {
        +chargePhone() void
    }

    PowerOutlet <|.. LaptopAdapter
    PowerOutlet <|.. RefrigeratorAdapter
    PowerOutlet <|.. SmartphoneAdapter

    LaptopAdapter --> Laptop : adapts
    RefrigeratorAdapter --> Refrigerator : adapts
    SmartphoneAdapter --> SmartphoneCharger : adapts
