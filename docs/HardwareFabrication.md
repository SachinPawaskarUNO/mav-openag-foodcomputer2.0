# Fabrication of the Box

:house: [Back to Main](./CompleteGuideFoodComputer.md)
We procured all the components from OpenAgriculture Supply to help us build the Food Computer device.
Useful youtube link to build the skeleton frame is available [here](https://www.youtube.com/watch?v=Uf1FqjcPWsI). This is a 45 minute silent video that walks you with the build.

# Build Instructions

Inorder to have a reference of all the materials procured, have a copy of [BOM](./BoM/BOM_MASTER.xlsx)

Follow the instructions below for assembling each modules-

1. [Assembling Frame](./Instructions/frame.md)
2. [Building Electronics Panel](./Instructions/electronics_panel.md)
3. [Build of the Brain Module](./Instructions/brain_module.md)
4. [Light Panel](./Instructions/light_panel.md)
5. [Power Module](./Instructions/power_module.md)
6. [Water Manifold](./Instructions/water_manifold.md)
7. [Chillers](./Instructions/chiller.md)
8. [Temperature Control](./Instructions/temperature_control_module.md)

## Set Electrical Components into Proper Modes
1. Set the **Multifunction Relay** into **Mode 10** and **Timer 1** to 20 seconds
1. Tune the **Pulse Generator** to **140Hz**
1. Set the **Atlas Circuits** into **I2C Mode**
1. On the **Signal Board** off solder points below both BNC Jacks and tape over w/electrical or kapton tape

## Mounting the Electronics panel
1. place the electronics panel in the partially assembled frame. Loosely fasten in place with a few **S-018-32-075-PST-F-AL(Bag 31)** binder posts along each side side.

## Mount chamber side components to the electronics panel
 1. Panel is mounted and the insulation is in place:
 1. Mount the Temperature Control Module, air flush out, and aeration pump to their respective zones in the electronics panel.

## Mounting the Frame Top Section
1. Mount the Top section of the frame. Line up the Appropriate Frame connectors, gradually tapping each connector in a small amount with each hit.

## Mount the Power Supply Assembly
1. Mount the Power Supply Assembly to the top of the electical box using three **S-025-20-438-BTN-S-SS (Bag 26)** 1/4-20 screws.
1. Connect the power supply wires to the appropriate places on the brain manifold.

## Mounting the Body Panels
1. Mount the Rest of the Body panels. When aligning for mounting, notice the small etched markings indicating the orientation of the panel. Each of these markings faces inward, have an arrow and word to show orientation, and most line up with the marking of an adjacent panel.

## Final Integration
- Reference the CAD model for final integration and watch [the build video](https://youtu.be/Uf1FqjcPWsI)!

## Final Integration Notes
 - When installing the air temperature and humidity sensor, wrap a piece of electrical tape around the base so it makes a snug fit with the mount.

Reference: [OpenAgInitiative-PFC2Build](https://github.com/OpenAgInitiative/openag_pfc2)
