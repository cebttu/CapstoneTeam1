
## Functionality
The power subsystem is the system that will provide power to all the components of the other subsystems on the robot. The power subsystem will also be responsible for hosting the emergency off switch in case of an error occurring. The power subsystems power supply will be a 2 7.4 volt 5200 maH batteries that will be connected to a distribution board that will split the power from the battery to all the subsystems.  

## Specifications and Restraints
| Number | Constraint component | Constraint description | Origin |
|--------|----------------------|------------------------|--------|
| 1. | Wires | The power subsystem shall use wire that can host up to 6 amps as the battery is capable of providing 5.2 amps per hour to prevent overheating and possible fire. | ASTM B258-18 |
| 2. |  Emergency Switch | The power subsystem shall have an emergency off switch that will cut power to all components of the robot  | Competition Specifications |
| 3. | Battery | The battery shall supply at least 5 amp per hour to ensure there is enough current supplied for the demand of the load | ASTM F963-17 |
| 4. | Fuse | The power subsystem shall have fuses in place to protect all the subsystem components from overcurrent    | IEC 60127 |


## Buildable Schematic

Wiring Diagram

![Alt text](https://github.com/cebttu/CapstoneTeam1/blob/Adrin11-signoffs-Power/Documentation/Images/Powe-Images/Wiring%20chart.PNG)

Main Power Distribution

![Alt text](https://github.com/cebttu/CapstoneTeam1/blob/Adrin11-signoffs-Power/Documentation/Images/Powe-Images/MAIN.png)

Arduino Power Connections

![Alt text](https://github.com/cebttu/CapstoneTeam1/blob/Adrin11-signoffs-Power/Documentation/Images/Powe-Images/MC.png)

Drive Train Power Connections

![Alt text](https://github.com/cebttu/CapstoneTeam1/blob/Adrin11-signoffs-Power/Documentation/Images/Powe-Images/Drive_T.png)