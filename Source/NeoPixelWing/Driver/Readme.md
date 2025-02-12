# Meadow.Foundation.FeatherWings.NeoPixelWing

**AdaFruit NeoPixel FeatherWing**

The **NeoPixelWing** library is included in the **Meadow.Foundation.FeatherWings.NeoPixelWing** nuget package and is designed for the [Wilderness Labs](www.wildernesslabs.co) Meadow .NET IoT platform.

This driver is part of the [Meadow.Foundation](https://developer.wildernesslabs.co/Meadow/Meadow.Foundation/) peripherals library, an open-source repository of drivers and libraries that streamline and simplify adding hardware to your C# .NET Meadow IoT applications.

For more information on developing for Meadow, visit [developer.wildernesslabs.co](http://developer.wildernesslabs.co/).

To view all Wilderness Labs open-source projects, including samples, visit [github.com/wildernesslabs](https://github.com/wildernesslabs/).

## Setup

Since the NeoPixel uses the WS2812 LED driver the NeoPixel FeatherWing can be controlled via the SPI COPI (MOSI) pin. 

Out of box the FeatherWing control pin is not mapped to the correct pin to allow it to be plug-and-ply with the F7 headers. The FeatherWing has many jumpers on the bottom to allow for changing the control pin to match your scenario.
Instructions on changing the control pin can be found with the [pinouts](https://learn.adafruit.com/adafruit-neopixel-featherwing/pinouts).

In order to align with the headers on the F7 the control pin on the FeatherWing should be changed to pin #12 [schematic](https://learn.adafruit.com/adafruit-neopixel-featherwing/download). 

## Installation

You can install the library from within Visual studio using the the NuGet Package Manager or from the command line using the .NET CLI:

`dotnet add package Meadow.Foundation.FeatherWings.NeoPixelWing`
## Usage

```csharp
NeoPixelWing neoWing;
MicroGraphics graphics;

public override Task Initialize()
{
    Console.WriteLine("Initializing ...");

    neoWing = new NeoPixelWing(Device.CreateSpiBus());

    graphics = new MicroGraphics(neoWing);

    return Task.CompletedTask;
}

public override Task Run()
{
    graphics.Clear();

    graphics.DrawRectangle(0, 0, 8, 4, false);

    graphics.Show();

    return Task.CompletedTask;
}

```
## How to Contribute

- **Found a bug?** [Report an issue](https://github.com/WildernessLabs/Meadow_Issues/issues)
- Have a **feature idea or driver request?** [Open a new feature request](https://github.com/WildernessLabs/Meadow_Issues/issues)
- Want to **contribute code?** Fork the [Meadow.Foundation.Featherwings](https://github.com/WildernessLabs/Meadow.Foundation.Featherwings) repository and submit a pull request against the `develop` branch


## Need Help?

If you have questions or need assistance, please join the Wilderness Labs [community on Slack](http://slackinvite.wildernesslabs.co/).
## About Meadow

Meadow is a complete, IoT platform with defense-grade security that runs full .NET applications on embeddable microcontrollers and Linux single-board computers including Raspberry Pi and NVIDIA Jetson.

### Build

Use the full .NET platform and tooling such as Visual Studio and plug-and-play hardware drivers to painlessly build IoT solutions.

### Connect

Utilize native support for WiFi, Ethernet, and Cellular connectivity to send sensor data to the Cloud and remotely control your peripherals.

### Deploy

Instantly deploy and manage your fleet in the cloud for OtA, health-monitoring, logs, command + control, and enterprise backend integrations.


