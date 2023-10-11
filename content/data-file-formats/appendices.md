+++
title = "Appendix: Enumerations"
weight = 300
+++

These appendices document the following enumerations:

- [Classifications](#classifications)
- [Constellations](#constellations)
- [Taxonomy Terms](#taxonomy)


# Classifications

“Classification” entries in WTML files can take one of the following values. The
default classification is **Unfiltered**.

- `Star`
- `Supernova`
- `BlackHole`
- `NeutronStar`
- `DoubleStar`
- `MultipleStars`
- `Asterism`
- `Constellation`
- `OpenCluster`
- `GlobularCluster`
- `NebulousCluster`
- `Nebula`
- `EmissionNebula`
- `PlanetaryNebula`
- `ReflectionNebula`
- `DarkNebula`
- `GiantMolecularCloud`
- `SupernovaRemnant`
- `InterstellarDust`
- `Quasar`
- `Galaxy`
- `SpiralGalaxy`
- `IrregularGalaxy`
- `EllipticalGalaxy`
- `Knot`
- `PlateDefect`
- `ClusterOfGalaxies`
- `OtherNGC`
- `Unidentified`
- `SolarSystem`
- `Unfiltered`
- `Stellar`
- `StellarGroupings`
- `Nebulae`
- `Galactic`
- `Other`


# Constellations

The following table lists the constellation codes and the center of each
constellation. If a correct code is entered in a WTML file, such as
`Constellation="CET"`, then there can be an improvement in the system’s
performance. If the **Constellation** field is left blank, or is wrong, then
the **RA** and **Dec** entries are used. There are 89 entries in the table, as
the discontiguous Serpens constellation is treated as two separate objects.


| Name | Code | RA (decimal hours) | RA (decimal degrees) | Dec (decimal degrees) |
| :-- | :-- | :-- | :-- | :-- |
| Andromeda | AND | 0.80766667 | 12.115 | 37.431833 |
| Antlia | ANT | 10.273833 | 154.1075 | -31.5165 |
| Apus | APS | 16.144167 | 242.1625 | -74.7 |
| Aquarius | AQR | 22.289667 | 334.345 | -9.210833 |
| Aquila | AQL | 19.667 | 295.005 | 3.410833 |
| Ara | ARA | 17.374833 | 260.6225 | -55.411667 |
| Aries | ARI | 2.636 | 39.54 | 20.79233 |
| Auriga | AUR | 6.0736667 | 91.105 | 42.028 |
| Bootes | BOO | 14.710667 | 220.66 | 31.202667 |
| Caelum | CAE | 4.7045 | 70.5675 | -36.11833 |
| Camelopardalis | CAM | 6.000 | 90.0 | 72.000 |
| Cancer | CNC | 8.649333 | 129.74 | 19.805833 |
| Canes Venatici | CVN | 13.116 | 196.74 | 40.101833 |
| Canis Major | CMA | 6.829 | 102.435 | -21.859667 |
| Canis Minor | CMI | 7.652833 | 114.7925 | 6.4271667 |
| Capricornus | CAP | 21.048833 | 315.7325 | -17.976833 |
| Carina | CAR | 8.695 | 130.425 | -62.780667 |
| Cassiopeia | CAS | 1.319333 | 19.79 | 62.184 |
| Centaurus | CEN | 13.071167 | 196.0675 | -46.654667 |
| Cepheus | CEP | 22.0 | 330.0 | 71.0085 |
| Cetus | CET | 1.668333 | 25.025 | -6.8206667 |
| Chamaeleon | CHA | 10.692167 | 160.3825 | -78.795 |
| Circinus | CIR | 15.0 | 225.0 | -64.0 |
| Columba | COL | 5.8626667 | 87.94 | -34.9055 |
| Coma Berenices | COM | 12.787833 | 191.8175 | 23.305667 |
| Corona Australis | CRA | 18.6465 | 279.6975 | -40.8525 |
| Corona Borealis | CRB | 15.843167 | 237.6475 | 32.624833 |
| Corvus | CRV | 12.442 | 186.63 | -17.56333 |
| Crater | CRT | 11.395833 | 170.9375 | -14.071 |
| Crux | CRU | 12.449833 | 186.7475 | -59.8135 |
| Cygnus | CYG | 20.588 | 308.82 | 44.545 |
| Delphinus | DEL | 20.6935 | 310.4025 | 11.671 |
| Dorado | DOR | 5.241833 | 78.6275 | -58.613 |
| Draco | DRA | 15.0 | 225.0 | 62.0 |
| Equuleus | EQU | 21.187667 | 317.815 | 7.7581667 |
| Eridanus | ERI | 4.0 | 60.0 | -27.243833 |
| Fornax | FOR | 2.798 | 41.97 | -30.3655 |
| Gemini | GEM | 7.0706667 | 106.06 | 22.600167 |
| Grus | GRU | 22.4565 | 336.8475 | -45.648167 |
| Hercules | HER | 17.386 | 260.79 | 27.498833 |
| Horologium | HOR | 3.276 | 49.14 | -52.663667 |
| Hydra | HYA | 11.612167 | 174.1825 | -26.0 |
| Hydrus | HYI | 2.3441667 | 35.1625 | -68.0435 |
| Indus | IND | 21.972167 | 329.5825 | -58.29333 |
| Lacerta | LAC | 22.46133 | 336.92 | 46.041833 |
| Leo | LEO | 10.667167 | 160.0075 | 13.138667 |
| Leo Minor | LMI | 10.24533 | 153.68 | 32.134667 |
| Lepus | LEP | 5.565833 | 83.4875 | -18.953667 |
| Libra | LIB | 15.19933 | 227.99 | -14.76533 |
| Lupus | LUP | 15.220167 | 228.3025 | -41.291167 |
| Lynx | LYN | 7.9921667 | 119.8825 | 47.466667 |
| Lyra | LYR | 18.852833 | 282.7925 | 36.68933 |
| Mensa | MEN | 5.415 | 81.225 | -76.496 |
| Microscopium | MIC | 20.964667 | 314.47 | -35.725167 |
| Monoceros | MON | 7.0605 | 105.9075 | 0.28216667 |
| Musca | MUS | 12.588 | 188.82 | -69.839 |
| Norma | NOR | 15.903 | 238.545 | -50.6485 |
| Octans | OCT | 23.0 | 345.0 | -81.848 |
| Ophiuchus | OPH | 17.394833 | 260.9225 | -6.0876667 |
| Orion | ORI | 5.5765 | 83.6475 | 5.949 |
| Pavo | PAV | 19.611833 | 294.1775 | -64.2185 |
| Pegasus | PEG | 22.69733 | 340.46 | 19.46633 |
| Perseus | PER | 3.175 | 47.625 | 45.013167 |
| Phoenix | PHE | 0.9318333 | 13.9775 | -47.41933 |
| Pictor | PIC | 5.7076667 | 85.615 | -52.525833 |
| Pisces | PSC | 0.4828333 | 7.2425 | 13.687167 |
| Piscis Austrinus | PSA | 22.2845 | 334.2675 | -29.357833 |
| Puppis | PUP | 7.5 | 112.5 | -33.0 |
| Pyxis | PYX | 8.9526667 | 134.29 | -26.64833 |
| Reticulum | RET | 3.9211667 | 58.8175 | -58.0025 |
| Sagitta | SGE | 19.650833 | 294.7625 | 18.86133 |
| Sagittarius | SGR | 19.099 | 286.485 | -27.523167 |
| Scorpius | SCO | 16.30 | 244.5 | -30.0 |
| Sculptor | SCL | 0.438 | 6.57 | -31.911667 |
| Scutum | SCT | 18.673167 | 280.0975 | -8.111333 |
| Serpens Caput | SER1 | 15.69 | 235.35 | 10 |
| Serpens Cauda | SER2 | 18.25 | 273.75 | -6.0 |
| Sextans | SEX | 10.2715 | 154.0725 | -1.385333 |
| Taurus | TAU | 4.7021667 | 70.5325 | 14.877167 |
| Telescopium | TEL | 19.325667 | 289.885 | -50.963167 |
| Triangulum | TRI | 2.1845 | 32.7675 | 31.476 |
| Triangulum Australe | TRA | 16.0825 | 241.2375 | -64.612 |
| Tucana | TUC | 23.77733 | 356.66 | -64.17 |
| Ursa Major | UMA | 11.312667 | 169.69 | 50.721167 |
| Ursa Minor | UMI | 15.0 | 225.0 | 77.699833 |
| Vela | VEL | 9.577333 | 143.66 | -46.832833 |
| Virgo | VIR | 13.4065 | 201.0975 | -3.8415 |
| Volans | VOL | 7.7955 | 116.9325 | -68.198833 |
| Vulpecula | VUL | 20.23133 | 303.47 | 24.442667 |


# Taxonomy

The following table lists the taxonomy codes that can be used to classify
images. WorldWide Telescope has adopted the image hierarchy taxonomy
proposed by the International Virtual Observatory Alliance and the
[Virtual Astronomy Multimedia Project]'s (VAMP)
[Astronomy Visualization Metadata] (AVM) standard. As an example, a tour of
the Sea of Tranquility on the Moon could be classified as *Planet → Feature →
Surface → Impact*.

| Code | Description |
| :-- | :-- |
| 1 | Planet |
| 1.1 | *Type* |
| 1.1.1 | Terrestrial |
| 1.1.2 | Gas Giant |
| 1.2 | *Feature* |
| 1.2.1 | Surface |
| 1.2.1.1 | Mountain |
| 1.2.1.2 | Canyon |
| 1.2.1.3 | Volcanic |
| 1.2.1.4 | Impact |
| 1.2.1.5 | Erosion |
| 1.2.1.6 | Liquid |
| 1.2.1.7 | Ice |
| 1.2.2 | Atmosphere |
| 1.2.2.1 | Cloud |
| 1.2.2.2 | Storm |
| 1.2.2.3 | Belt |
| 1.2.2.4 | Aurora |
| 1.3 | *Special Cases* |
| 1.3.1 | Transiting |
| 1.3.2 | Hot Jupiter |
| 1.3.3 | Pulsar planet |
| 1.4 | Satellite |
| 1.4.1 | *Feature* |
| 1.4.1.1 | Surface |
| 1.4.1.1.1 | Mountain |
| 1.4.1.1.2 | Canyon |
| 1.4.1.1.3 | Volcanic |
| 1.4.1.1.4 | Impact |
| 1.4.1.1.5 | Erosion |
| 1.4.1.1.6 | Liquid |
| 1.4.1.1.7 | Ice |
| 1.4.1.2 | Atmosphere |
| 1.5 | Ring |
| 2 | Interplanetary Body |
| 2.1 | Dwarf planet |
| 2.2 | Comet |
| 2.2.1 | Nucleus |
| 2.2.2 | Coma |
| 2.2.3 | Tail |
| 2.2.3.1 | Dust |
| 2.2.3.2 | Gas |
| 2.3 | Asteroid |
| 2.4 | Meteoroid |
| 3 | Star |
| 3.1 | *Evolutionary Stage* |
| 3.1.1 | Protostar |
| 3.1.2 | Young Stellar Object |
| 3.1.3 | Main Sequence |
| 3.1.4 | Red Giant |
| 3.1.5 | Red Supergiant |
| 3.1.6 | Blue Supergiant |
| 3.1.7 | White Dwarf |
| 3.1.8 | Supernova |
| 3.1.9 | Neutron Star |
| 3.1.9.1 | Pulsar |
| 3.1.9.2 | Magnetar |
| 3.1.10 | Black Hole |
| 3.2 | *Type* |
| 3.2.1 | Variable |
| 3.2.1.1 | Pulsating |
| 3.2.1.2 | Irregular |
| 3.2.1.3 | Eclipsing |
| 3.2.1.4 | Flare Star |
| 3.2.1.5 | Nova |
| 3.2.2 | Carbon |
| 3.2.3 | Brown Dwarf |
| 3.2.4 | Wolf-Rayet |
| 3.2.5 | Blue Straggler |
| 3.2.6 | Exotic |
| 3.3 | *Spectral Type* |
| 3.3.1 | O |
| 3.3.2 | B |
| 3.3.3 | A |
| 3.3.4 | F |
| 3.3.5 | G |
| 3.3.6 | K |
| 3.3.7 | M |
| 3.3.8 | L |
| 3.3.9 | T |
| 3.4 | *Population* |
| 3.4.1 | I |
| 3.4.2 | II |
| 3.4.3 | III |
| 3.5 | *Feature* |
| 3.5.1 | Photosphere |
| 3.5.1.1 | Granulation |
| 3.5.1.2 | Sunspot |
| 3.5.2 | Chromosphere |
| 3.5.2.1 | Flare |
| 3.5.2.2 | Facula |
| 3.5.3 | Corona |
| 3.5.3.1 | Prominence |
| 3.6 | *Grouping* |
| 3.6.1 | Binary |
| 3.6.2 | Triple |
| 3.6.3 | Multiple |
| 3.6.4 | Cluster |
| 3.6.4.1 | Open |
| 3.6.4.2 | Globular |
| 3.7 | Circumstellar Material |
| 3.7.1 | Planetary System |
| 3.7.2 | Disk |
| 3.7.2.1 | Protoplanetary |
| 3.7.2.2 | Accretion |
| 3.7.2.3 | Debris |
| 3.7.3 | Outflow |
| 3.7.3.1 | Solar Wind |
| 3.7.3.2 | Coronal Mass Ejection |
| 4 | Nebula |
| 4.1 | *Type* |
| 4.1.1 | Interstellar Medium |
| 4.1.2 | Star Formation |
| 4.1.3 | Planetary |
| 4.1.4 | Supernova Remnant |
| 4.1.5 | Jet |
| 4.2 | *Appearance* |
| 4.2.1 | Emission |
| 4.2.1.1 | H-II Region |
| 4.2.2 | Reflection |
| 4.2.2.1 | Light Echo |
| 4.2.3 | Dark |
| 4.2.3.1 | Molecular Cloud |
| 4.2.3.2 | Bok Globule |
| 4.2.3.3 | Proplyd |
| 5 | Galaxy |
| 5.1 | *Type* |
| 5.1.1 | Spiral |
| 5.1.2 | Barred |
| 5.1.3 | Lenticular |
| 5.1.4 | Elliptical |
| 5.1.5 | Ring |
| 5.1.6 | Irregular |
| 5.1.7 | Interacting |
| 5.1.8 | Gravitationally Lensed |
| 5.2 | *Size* |
| 5.2.1 | Giant |
| 5.2.2 | Dwarf |
| 5.3 | *Activity* |
| 5.3.1 | Normal |
| 5.3.2 | AGN |
| 5.3.2.1 | Quasar |
| 5.3.2.2 | Seyfert |
| 5.3.2.3 | Blazar |
| 5.3.2.4 | Liner |
| 5.3.3 | Starburst |
| 5.3.4 | Ultraluminous |
| 5.4 | *Component* |
| 5.4.1 | Bulge |
| 5.4.2 | Bar |
| 5.4.3 | Disk |
| 5.4.4 | Halo |
| 5.4.5 | Ring |
| 5.4.6 | Central Black Hole |
| 5.4.7 | Spiral Arm |
| 5.4.8 | Dust Lane |
| 5.5 | *Grouping* |
| 5.5.1 | Pair |
| 5.5.2 | Multiple |
| 5.5.3 | Cluster |
| 5.5.4 | Supercluster |
| 6 | Cosmology |
| 6.1 | *Morphology* |
| 6.1.1 | Deep Field |
| 6.1.2 | Large-Scale Structure |
| 6.1.3 | Cosmic Background |
| 6.2 | *Phenomenon* |
| 6.2.1 | Lensing |
| 6.2.2 | Gamma Ray Burst |
| 6.2.3 | Dark Matter |
| 7 | Sky Phenomenon |
| 7.1 | Night Sky |
| 7.1.1 | Constellation |
| 7.1.2 | Asterism |
| 7.1.3 | Milky Way |
| 7.1.4 | Trail |
| 7.1.4.1 | Meteor |
| 7.1.4.2 | Star |
| 7.1.4.3 | Satellite |
| 7.1.5 | Zodiacal Light |
| 7.1.5.1 | Gegenschein |
| 7.1.6 | Night glow |
| 7.2 | Eclipse |
| 7.2.1 | Solar |
| 7.2.1.1 | Total |
| 7.2.1.2 | Partial |
| 7.2.1.3 | Annular |
| 7.2.2 | Lunar |
| 7.2.2.1 | Total |
| 7.2.2.2 | Partial |
| 7.2.2.3 | Penumbral |
| 7.2.3 | Occultation |
| 7.2.4 | Transit |
| 7.3 | Light Phenomenon |
| 7.3.1 | Sunrise-Sunset |
| 7.3.1.1 | Green flash |
| 7.3.1.2 | Refractive Distortion |
| 7.3.1.3 | Sun Pillar |
| 7.3.2 | Cloud |
| 7.3.2.1 | Iridescent |
| 7.3.2.2 | Noctilucent |
| 7.3.2.3 | Nacreous |
| 7.3.2.4 | Corona |
| 7.3.2.5 | Glory |
| 7.3.3 | Rainbow |
| 7.3.3.1 | Moonbow |
| 7.3.3.2 | Fogbow |
| 7.3.4 | Halo |
| 7.3.4.1 | Circle |
| 7.3.4.2 | Parhelia |
| 7.3.4.3 | Arc |
| 7.3.5 | Ray-Shadow |
| 7.3.5.1 | Crepuscular ray |
| 7.3.5.2 | Anti-crepuscular ray |
| 7.3.5.3 | Earth shadow |
| 7.3.6 | Lightning |
| 7.3.7 | Aurora |
| 8 | Technology |
| 8.1 | Observatory |
| 8.1.1 | Facility |
| 8.1.2 | Telescope |
| 8.1.3 | Instrument |
| 8.2 | Spacecraft |
| 8.2.1 | Orbiter |
| 8.2.2 | Probe |
| 8.2.3 | Lander |
| 8.2.4 | Manned |

[Virtual Astronomy Multimedia Project]: http://virtualastronomy.org/
[Astronomy Visualization Metadata]: https://www.virtualastronomy.org/avm_metadata.php
