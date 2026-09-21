# adapter-pattern

Java adapter pattern example for plugging different devices into a common `PowerOutlet` interface.

## Included types

- `PowerOutlet` with `plugIn()`
- Adaptees:
  - `Laptop` with `charge()`
  - `Refrigerator` with `startCooling()`
  - `SmartphoneCharger` with `chargePhone()`
- Adapters:
  - `LaptopAdapter`
  - `RefrigeratorAdapter`
  - `SmartphoneAdapter`

Run `AdapterPatternDemo` to see all three devices used through the common `PowerOutlet` target interface.