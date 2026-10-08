# Awesome Aerospace & Cyberspace Hacking

> A curated list of high-quality resources for researching the
> cybersecurity of **drones, aircraft, and satellites** --- including
> standards, threat models, academic research, open-source software, SDR
> tooling, datasets, labs, and practical learning material.

[![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

This list is intentionally focused on **authorized security research,
defensive engineering, education, and controlled laboratory work**.
Aerospace systems are safety-critical: test only systems, frequencies,
networks, and hardware you are explicitly authorized to test.

## Contents

-   [Drone Hacking](#drone-hacking)
    -   [Standards, Guidance & Threat
        Modeling](#drone-standards-guidance--threat-modeling)
    -   [Flight Stacks & Protocols](#drone-flight-stacks--protocols)
    -   [Research & Papers](#drone-research--papers)
    -   [Tools, Labs & Research
        Repositories](#drone-tools-labs--research-repositories)
    -   [RF, Telemetry & Ground
        Stations](#drone-rf-telemetry--ground-stations)
    -   [Conference Talks & Videos](#drone-conference-talks--videos)
    -   [Research Papers & Technical Reports](#drone-research-papers--technical-reports)
    -   [Vulnerability Research & Disclosure](#drone-vulnerability-research--disclosure)
-   [Airplane Hacking](#airplane-hacking)
    -   [Standards, Regulation &
        Guidance](#airplane-standards-regulation--guidance)
    -   [Aircraft Communications &
        Surveillance](#aircraft-communications--surveillance)
    -   [Open-Source SDR & Protocol
        Tools](#airplane-open-source-sdr--protocol-tools)
    -   [Threat Intelligence &
        Research](#airplane-threat-intelligence--research)
    -   [Research Topics](#airplane-research-topics)
    -   [Conference Talks & Videos](#airplane-conference-talks--videos)
    -   [Research Papers & Technical Reports](#airplane-research-papers--technical-reports)
    -   [Challenges, Labs & Practical Research](#airplane-challenges-labs--practical-research)
-   [Satellite Hacking](#satellite-hacking)
    -   [Standards, Guidance & Security
        Frameworks](#satellite-standards-guidance--security-frameworks)
    -   [Threat Modeling & Adversary
        Knowledge](#satellite-threat-modeling--adversary-knowledge)
    -   [Ground Stations, SDR &
        Telemetry](#satellite-ground-stations-sdr--telemetry)
    -   [Flight Software & Space
        Systems](#satellite-flight-software--space-systems)
    -   [Research & Datasets](#satellite-research--datasets)
    -   [Conference Talks & Videos](#satellite-conference-talks--videos)
    -   [Hack-A-Sat & Space CTFs](#hack-a-sat--space-ctfs)
    -   [Recent Research](#satellite-recent-research)

------------------------------------------------------------------------

# Drone Hacking

Uncrewed aircraft systems (UAS/UAVs) combine an aircraft, flight
controller, sensors, companion computers, ground-control software, radio
links, and often cloud/mobile infrastructure. Good drone security
research therefore needs to cover both **embedded/vehicle security** and
the **communications and ground segment**.

## Drone Standards, Guidance & Threat Modeling

-   [OWASP Drone Security Cheat
    Sheet](https://github.com/OWASP/CheatSheetSeries/blob/master/cheatsheets/Drone_Security_Cheat_Sheet.md)
    --- Practical overview of drone architecture, attack surfaces,
    common threats, and defensive controls.
-   [NIST --- Uncrewed Aircraft
    Systems](https://www.nist.gov/ctl/pscr/research-portfolios/uncrewed-aircraft-systems)
    --- NIST research covering UAS communications, public-safety
    applications, cybersecurity, and AI risk.
-   [CISA --- Be Air
    Aware](https://www.cisa.gov/topics/physical-security/be-air-aware)
    --- UAS cyber and physical-security guidance for critical
    infrastructure and public environments.
-   [ArduPilot ---
    Security](https://ardupilot.org/dev/docs/security-landing-page.html)
    --- Security documentation covering MAVLink signing, parameter
    lockdown, secure firmware, Remote ID, physical security, and
    vulnerability reporting.
-   [PX4 --- MAVLink Security
    Hardening](https://github.com/PX4/PX4-Autopilot/blob/main/docs/en/mavlink/security_hardening.md)
    --- Official PX4 guidance for securing MAVLink communications in
    production deployments.
-   [MAVLink --- Security](https://mavlink.io/en/guide/security.html)
    --- Protocol-level security documentation and message-signing
    concepts.
-   [MAVLink](https://mavlink.io/) --- The protocol specification and
    ecosystem documentation; essential background for UAV communication
    research.
-   [FAA --- Unmanned Aircraft Systems](https://www.faa.gov/uas) ---
    Primary U.S. regulatory and technical information for civil UAS
    operations.

## Drone Flight Stacks & Protocols

-   [PX4 Autopilot](https://github.com/PX4/PX4-Autopilot) --- Major
    open-source flight-control stack with SITL support and security
    documentation.
-   [ArduPilot](https://github.com/ArduPilot/ardupilot) --- Mature
    open-source autopilot supporting multicopters, planes, rovers, and
    other vehicles.
-   [MAVLink](https://github.com/mavlink/mavlink) --- Open protocol
    implementation and message definitions used extensively by PX4 and
    ArduPilot ecosystems.
-   [MAVROS](https://github.com/mavlink/mavros) --- ROS interface for
    MAVLink; useful when studying the interaction between robotics
    middleware and flight-control systems.
-   [QGroundControl](https://github.com/mavlink/qgroundcontrol) ---
    Open-source ground-control station for MAVLink-based vehicles.
-   [MAVSDK](https://github.com/mavlink/MAVSDK) --- SDK for interacting
    with MAVLink systems programmatically.
-   [Dronecode](https://www.dronecode.org/) --- Open-source drone
    ecosystem and project community around PX4 and related technologies.
-   [ROS 2
    Security](https://design.ros2.org/articles/ros2_dds_security.html)
    --- Security architecture for DDS-based robotic systems, relevant to
    modern companion-computer architectures.

## Drone Research & Papers

-   [A Survey on Cybersecurity Attacks and Defenses for Unmanned Aerial
    Systems](https://doi.org/10.1016/j.sysarc.2023.102870) --- Broad
    survey covering communication, software, payload, and
    autonomous-system security.
-   [A Systematic Approach for Threat and Vulnerability Analysis of
    Unmanned Aerial Vehicles](https://doi.org/10.1016/j.iot.2024.101180)
    --- Threat modeling and penetration-testing research focused on UAV
    systems and MAVLink.
-   [MAVLink Protocol: A Survey of Security Threats and
    Countermeasures](https://doi.org/10.1109/ICoDT262145.2024.10740195)
    --- Review of MAVLink-specific security issues and countermeasures.
-   [MAVSec: Securing the MAVLink Protocol for Ardupilot/PX4 Unmanned
    Aerial Systems](https://arxiv.org/abs/1905.00265) --- Research into
    confidentiality and security mechanisms for MAVLink.
-   [Mission-preserving protocol defense: An in-situ MAVLink
    honeypot](https://doi.org/10.1016/j.comcom.2026.108613) --- Recent
    research on defensive deception and MAVLink protocol monitoring.

## Drone Tools, Labs & Research Repositories

-   [Awesome Drone
    Hacking](https://github.com/nicholasaleks/Awesome-Drone-Hacking) ---
    Dedicated curated collection of drone-hacking tools, research,
    talks, RTOS resources, flight-controller material, telemetry, and RF
    topics.
-   [ArduPilot
    SITL](https://ardupilot.org/dev/docs/sitl-simulator-software-in-the-loop.html)
    --- Software-in-the-loop environment for testing ArduPilot without
    flying a real aircraft.
-   [PX4 Simulation](https://docs.px4.io/main/en/simulation/) --- PX4
    simulation documentation for safe, repeatable research.
-   [ArduPilot Security
    Research](https://github.com/hassan-hfk/Ardupilot-Drone-Security-Research)
    --- Example research using ArduPilot SITL for traffic analysis,
    geofencing, and controlled security experiments.
-   [Drone Audit
    Framework](https://github.com/Megh089/drone-audit-framework) ---
    Experimental audit tooling for MAVLink-based drones, including
    packet fuzzing and SITL-oriented checks.
-   [MAVLink Fuzzer](https://github.com/designersden/mavlink-fuzzer) ---
    Research project exploring fuzzing of MAVLink libraries.
-   [OWASP](https://owasp.org/) --- Useful broader application-security
    methodologies for drone GCS applications, APIs, companion computers,
    and cloud backends.
-   [American Fuzzy Lop++](https://github.com/AFLplusplus/AFLplusplus)
    --- General-purpose coverage-guided fuzzing framework useful for
    flight-stack and protocol parsers in controlled environments.
-   [libFuzzer](https://llvm.org/docs/LibFuzzer.html) --- In-process
    fuzzing framework suitable for parsers and embedded protocol
    libraries.

## Drone RF, Telemetry & Ground Stations

-   [GNU Radio](https://www.gnuradio.org/) --- Open-source SDR framework
    for analyzing radio systems and building controlled research
    receivers.
-   [GNU Radio GitHub](https://github.com/gnuradio/gnuradio) --- Source
    code and development ecosystem.
-   [Universal Radio Hacker](https://github.com/jopohl/urh) ---
    SDR-oriented protocol analysis and reverse-engineering framework;
    use only on authorized signals.
-   [Inspectrum](https://github.com/miek/inspectrum) --- Signal-analysis
    tool for inspecting recorded RF samples.
-   [Kismet](https://www.kismetwireless.net/) --- Wireless network
    discovery and monitoring platform useful for studying the network
    side of drone systems.
-   [Wireshark](https://www.wireshark.org/) --- Packet analysis for
    MAVLink-over-IP, GCS networks, companion-computer traffic, and lab
    environments.
-   [MAVLink Inspector in
    QGroundControl](https://docs.qgroundcontrol.com/master/en/qgc-user-guide/analyze_view/mavlink_inspector.html)
    --- Useful for inspecting MAVLink traffic in a controlled lab.
-   [MAVLink Router](https://github.com/mavlink-router/mavlink-router)
    --- MAVLink routing daemon useful for building segmented test
    networks.

------------------------------------------------------------------------


## Drone Conference Talks & Videos

A practical way to get into drone security is to watch researchers demonstrate the real attack surface before trying to reproduce anything in a lab. The following talks are especially useful for learning the terminology, architecture, RF layer, flight-controller ecosystem, and common research methodology.

- [WTF WJI, UAV CTF?](https://media.ccc.de/v/camp2023-125-wtf_wji_uav_ctf) — Felix Domke, Chaos Communication Camp 2023; a useful bridge between UAV systems and CTF-style research.
- [Demodulating 5GHz Analog Drone Video](https://www.youtube.com/watch?v=rl8ACNnjPFA) — Practical RF/FPV signal-analysis work.
- [Parrot Drones Hijacking](https://www.youtube.com/watch?v=66z-aXy_1Yo) — Pedro Cabrera, RSA Conference 2018.
- [A Drone Tale — All Your Drones Are Belong to Us](https://www.youtube.com/watch?v=0oSxvC8D3XU) — Paolo Stagno, Hacktivity.
- [All Your Bebop Drones Still Belong to Us](https://www.youtube.com/watch?v=ra0nKHvaXnc) — Pedro Cabrera, RootedCON 2016.
- [Shelling Out a “Smart Drone”](https://www.youtube.com/watch?v=IqCz-V6WMVg) — Kevin Finisterre, DerbyCon 2015.
- [Drones Hijacking — Multi Dimensional Attack Vectors](https://www.youtube.com/watch?v=DFLofy789ko) — Aaron Luo, DEF CON 24.
- [Hacking a Professional Drone](https://www.youtube.com/watch?v=JRVb-xE1zTI) — Nils Rodday, Black Hat 2016.
- [Avoiding CounterDrone Systems with NanoDrones](https://www.youtube.com/watch?v=pVmFxJPOu9I) — DEF CON 26.
- [Game of Drones](https://www.youtube.com/watch?v=iG7hUE2BZZo) — DEF CON 25.
- [Spread Spectrum Techniques for Anti-Drone Evasion](https://www.youtube.com/watch?v=8Ng91UY3D2M) — DEF CON 31.
- [Practical Aerial Hacking & Surveillance](https://www.youtube.com/watch?v=knrvrR-B1ZI) — DEF CON 22.
- [Icarus — Hacking and Hijacking DSMx Drones & RC Devices](https://www.youtube.com/watch?v=abl6oOxLRXs) — PACSEC 2016.
- [Hacking WITH Drones](https://www.youtube.com/watch?v=M0BDHT43Ucc) — Matt Gaffney, DEF CON 29 Aerospace Village.

> Some older drone talk URLs move over time. When a conference archive or speaker upload exists, prefer the canonical conference-hosted copy.

## Drone Research Papers & Technical Reports

- [Vulnerability Analysis of the MAVLink Protocol for Command and Control of Unmanned Aircraft](https://apps.dtic.mil/sti/citations/ADA612523) — Widely cited technical analysis of MAVLink confidentiality, integrity, and availability limitations.
- [Unmanned Aircraft Capture and Control via GPS Spoofing](https://rnl.ae.utexas.edu/images/stories/files/papers/rohde_schroeder.pdf) — Seminal GPS-spoofing research against autonomous aircraft.
- [GPS Jamming Techniques for UAVs Using Low-Cost SDR Platforms](https://www.researchgate.net/publication/326532032_GPS_Jamming_Techniques_for_UAVs_using_Low-Cost_SDR_Platforms) — SDR-based navigation-security research.
- [Drone Detection and Tracking Using RF Identification Signals](https://www.mdpi.com/2079-9292/12/19/4038) — RF/Remote-ID oriented research with practical signal-processing implications.
- [A Survey on Cybersecurity Attacks and Defenses for Unmanned Aerial Systems](https://doi.org/10.1016/j.sysarc.2023.102870) — Broad UAS cybersecurity survey covering architecture, threats, and mitigations.
- [MAVLink Security: A Survey of Threats and Countermeasures](https://arxiv.org/abs/1905.00265) — Useful introduction to MAVLink-specific security considerations.
- [A Systematic Approach for Threat and Vulnerability Analysis of Unmanned Aerial Vehicles](https://doi.org/10.1016/j.iot.2024.101180) — Threat-analysis methodology for UAV systems.
- [Mission-preserving protocol defense: An in-situ MAVLink honeypot](https://doi.org/10.1016/j.comcom.2026.108613) — Recent work on defensive monitoring and deception for MAVLink environments.

## Drone Vulnerability Research & Disclosure

- [DJI Security](https://security.dji.com/) — Official vulnerability disclosure and security research portal.
- [Parrot Security / Bug Bounty](https://www.parrot.com/en/security) — Vendor-side security and responsible-disclosure resources.
- [PX4 Security](https://px4.io/security/) — Official PX4 security policy and reporting guidance.
- [ArduPilot Security](https://ardupilot.org/dev/docs/security-landing-page.html) — Security reporting, hardening, and defensive documentation.
- [QGroundControl Security](https://github.com/mavlink/qgroundcontrol/security) — Security reporting path for the ground-control application.
- [Robot Vulnerability Database (RVD)](https://www.robotvulnerabilitydatabase.com/) — Vulnerability tracking for robotics and autonomous systems.
- [NVD](https://nvd.nist.gov/) — Search CVEs affecting flight stacks, companion computers, libraries, mobile GCS applications, and embedded components.
- [CVE](https://www.cve.org/) — Canonical vulnerability identifiers for published drone/robotics security issues.

# Airplane Hacking

Aircraft cybersecurity spans avionics, passenger information systems,
airline IT, airport systems, air-traffic management, aircraft-to-ground
links, wireless interfaces, navigation/surveillance technologies, and
the wider aviation supply chain. A strong research workflow separates
**safety-critical avionics** from **enterprise/ground infrastructure**
and treats them as different security domains.

## Airplane Standards, Regulation & Guidance

-   [ICAO Aviation Cybersecurity
    Strategy](https://www.icao.int/aviation-cybersecurity/strategy) ---
    Global civil-aviation cybersecurity strategy built around
    international cooperation, governance, regulation, information
    sharing, incident management, and capacity building.
-   [ICAO Cybersecurity Action
    Plan](https://www.icao.int/aviation-cybersecurity/action-plan) ---
    Practical implementation framework for the ICAO cybersecurity
    strategy.
-   [ICAO Global Cyber Risk Considerations --- Doc
    10213](https://www.icao.int/aviation-cybersecurity/Doc10213) ---
    Guidance for integrating cyber-risk management into aviation safety,
    security, and air-navigation processes.
-   [ICAO Aviation Cybersecurity Guidance
    Material](https://www.icao.int/aviation-cybersecurity/guidance-material)
    --- Collection of ICAO guidance covering cyber information sharing,
    policy, ATM security, and cybersecurity culture.
-   [ICAO Manual on Aviation Information Security --- Doc
    10204](https://store.icao.int/en/manual-on-aviation-information-security-doc-10204)
    --- 2025 manual addressing confidentiality, integrity, availability,
    and information-security objectives in aviation.
-   [EASA Part-IS](https://www.easa.europa.eu/en/domains/cyber-security)
    --- European aviation information-security regulatory framework.
-   [EASA Easy Access Rules for Information
    Security](https://www.easa.europa.eu/en/document-library/easy-access-rules/easy-access-rules-information-security-regulations-eu-2023203-and-20221645)
    --- Consolidated Part-IS rules and associated acceptable means of
    compliance/guidance.
-   [RTCA](https://www.rtca.org/) --- Major aviation standards
    organization; search its publications for aircraft
    information-security and airworthiness-security standards such as
    the DO-326/DO-356 family.
-   [EUROCONTROL](https://www.eurocontrol.int/) --- European ATM
    organization with substantial material on aviation and ATM
    cybersecurity.
-   [CANSO](https://canso.org/) --- Air navigation services organization
    with cybersecurity guidance and aviation-sector security material.

## Airplane Communications & Surveillance

-   [ADS-B](https://www.faa.gov/air_traffic/technology/adsb) --- FAA
    overview of Automatic Dependent Surveillance-Broadcast.
-   [OpenSky Network](https://opensky-network.org/) ---
    Research-oriented network providing access to large-scale ADS-B and
    Mode-S data.
-   [OpenSky API](https://github.com/openskynetwork/opensky-api) ---
    Open-source API documentation and tooling for aircraft state and
    historical data.
-   [Mode S / ADS-B overview](https://mode-s.org/) --- Technical
    material by Junzi Sun on aircraft surveillance technologies and
    signal processing.
-   [ACARS](https://en.wikipedia.org/wiki/ACARS) --- Useful protocol
    background; pair with primary/technical sources and decoder
    documentation.
-   [libacars](https://github.com/szpajder/libacars) --- Library for
    decoding ACARS payloads and higher-layer applications including
    CPDLC and ADS-C.
-   [dumpvdl2](https://github.com/szpajder/dumpvdl2) --- VDL Mode 2
    decoder and protocol analyzer.
-   [dumphfdl](https://github.com/szpajder/dumphfdl) --- High Frequency
    Data Link decoder.
-   [JAERO](https://github.com/szpajder/JAERO) --- Decoder for
    Aero/SatCom signals carrying aircraft communications.
-   [ACARSDEC](https://github.com/f00b4r0/acarsdec) --- SDR-based ACARS
    decoder.
-   [Mode-S.org](https://mode-s.org/) --- Technical educational resource
    covering Mode-S, ADS-B, and aircraft surveillance.

## Airplane Open-Source SDR & Protocol Tools

-   [dump1090](https://github.com/antirez/dump1090) --- Classic
    Mode-S/ADS-B decoder for RTL-SDR.
-   [readsb](https://github.com/wiedehopf/readsb) --- Modern
    ADS-B/Mode-S decoder with extensive JSON and networking support.
-   [tar1090](https://github.com/wiedehopf/tar1090) --- Web interface
    and historical visualization layer for ADS-B decoders.
-   [gr-air-modes](https://github.com/bistromath/gr-air-modes) --- GNU
    Radio Mode-S/ADS-B receiver.
-   [RTL-SDR](https://www.rtl-sdr.com/) --- Widely used low-cost SDR
    platform for receive-only aviation research.
-   [rtl-sdr GitHub](https://github.com/osmocom/rtl-sdr) --- Core
    RTL-SDR software.
-   [GNU Radio](https://github.com/gnuradio/gnuradio) --- SDR framework
    for building and analyzing aviation signal-processing experiments.
-   [Airspy](https://airspy.com/) --- SDR hardware platform useful for
    higher-performance RF research.
-   [SigDigger](https://github.com/BatchDrake/SigDigger) --- SDR
    spectrum-analysis and demodulation application.
-   [inspectrum](https://github.com/miek/inspectrum) --- Visual analysis
    of recorded digital signals.

## Airplane Threat Intelligence & Research

-   [MITRE ATT&CK --- TA2541](https://attack.mitre.org/groups/G1018/)
    --- ATT&CK profile for a threat actor targeting aviation, aerospace,
    transportation, manufacturing, and defense organizations.
-   [MITRE ATT&CK](https://attack.mitre.org/) --- Useful general
    threat-modeling and adversary-behavior framework for aviation IT and
    supporting infrastructure.
-   [CISA](https://www.cisa.gov/) --- U.S. government cybersecurity
    guidance and advisories applicable to aviation operators and
    critical infrastructure.
-   [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)
    --- General framework useful for airline, airport, ATM, and aviation
    enterprise environments.
-   [Aviation Information Sharing and Analysis
    Center](https://www.a-isac.org/) --- Sector-oriented information
    sharing and threat intelligence for aviation.
-   [ENISA](https://www.enisa.europa.eu/) --- European cybersecurity
    agency with guidance relevant to transport and aviation.
-   [EASA
    Cybersecurity](https://www.easa.europa.eu/en/domains/cyber-security)
    --- Regulatory and technical material for aviation information
    security.
-   [ICAO Cybersecurity](https://www.icao.int/aviation-cybersecurity)
    --- Primary international aviation-cybersecurity hub.

## Airplane Research Topics

Good research areas include:

-   **ADS-B security** --- authentication, integrity, privacy, spoofing
    detection, multilateration, and receiver security.
-   **Mode-S** --- protocol analysis, receiver implementation security,
    and signal integrity.
-   **ACARS / VDL2 / HFDL** --- protocol parsing, message integrity,
    decoder security, and data-link architecture.
-   **CPDLC / ADS-C** --- higher-layer aviation data-link security and
    trust boundaries.
-   **Aircraft network segmentation** --- interactions between avionics,
    passenger domains, maintenance systems, and external connectivity.
-   **Avionics buses** --- ARINC 429, ARINC 664/AFDX, CAN/CANaerospace,
    MIL-STD-1553, and related embedded buses.
-   **Flight-management and navigation systems** --- secure software
    engineering, input validation, resilience, and assurance.
-   **Ground systems** --- airline operational systems, airport systems,
    maintenance networks, dispatch, and air-traffic-management
    infrastructure.
-   **Supply-chain security** --- firmware, third-party components,
    maintenance tooling, and software update processes.
-   **Safety/security convergence** --- understanding how cybersecurity
    failures can propagate into safety-relevant conditions.

------------------------------------------------------------------------


## Airplane Conference Talks & Videos

- [DEF CON 20: Hackers + Airplanes](https://www.youtube.com/watch?v=CXv1j3GbgLk) — Classic introduction to the aircraft-security research scene.
- [DEF CON 27: Behind the Scenes of Hacking Airplanes](https://www.youtube.com/watch?v=IgKsH6BzQWY) — Useful background on how aircraft security research is approached in practice.
- [MIL-STD-1553 Avionics Bus Overview](https://www.youtube.com/watch?v=36dj_hPDGHM) — Helpful primer before diving into avionics-bus security.
- [Can Aircraft Be Hacked?!](https://www.youtube.com/watch?v=rVs8RSA8UMs) — Pilot-oriented overview of aircraft attack surfaces.
- [Spacecraft Technology: Data Busses](https://www.youtube.com/watch?v=dD7VwwlGRw8) — Useful cross-domain introduction to aerospace data buses.
- [Aerospace Village — DEF CON 29](https://www.aerospacevillage.org/defcon-29) — Conference schedule with aviation and space sessions, workshops, and speaker material.
- [DEF CON 32 Aerospace Village Schedule](https://www.defcon.outel.org/defcon32/dc32-consolidated_page_split_Vil.html) — Includes aviation talks, flight challenges, drone activities, and space-security workshops.
- [Hacking EFBs: Engine Performance](https://www.pentestpartners.com/security-blog/def-con-30-hacking-efbs-engine-performance/) — Pen Test Partners' DEF CON 30 research on electronic flight bag data and flight-safety implications.
- [CAN Bus in Aviation: Investigating CAN Bus in Avionics](https://github.com/whoami-chmod777/Awesome-Industrial-Protocols) — Useful pointer to a DEF CON Aviation Village session on CAN-based avionics research.

## Airplane Research Papers & Technical Reports

- [Evaluating the Security of Aircraft Systems](https://arxiv.org/abs/2209.04028) — Comprehensive review and taxonomy of aircraft systems, attack surfaces, and adversarial techniques.
- [In Pursuit of Aviation Cybersecurity: Experiences and Lessons From a Competitive Approach](https://doi.org/10.1109/MSEC.2023.3265523) — Competition-driven research into aviation cybersecurity and passive aircraft localization.
- [A Framework for Aviation Cybersecurity](https://ieeexplore.ieee.org/document/8556747) — Graph-based framework and taxonomy for aviation cybersecurity with ADS-B as a case study.
- [Cyber-Security Challenges in Aviation Industry: A Review of Current and Future Trends](https://arxiv.org/abs/2107.04910) — Broad literature review spanning aviation IT, airports, aircraft, and emerging systems.
- [Cybersecurity in Aviation: An Intrinsic Review](https://doi.org/10.1109/ICCUBEA47591.2019.9128483) — Review of aviation-sector cybersecurity concerns and attack surfaces.
- [Aviation Data Networks: Security Issues and Network Architecture](https://doi.org/10.1109/MAES.2005.1453803) — Foundational paper on security considerations for aircraft data networks.
- [Security and Performance Comparison of Different Secure Channel Protocols for Avionics Wireless Networks](https://arxiv.org/abs/1608.04115) — Research on secure communications for avionics wireless networking.
- [The Missing Link: Aircraft Cybersecurity at the Operational Level](https://doi.org/10.4271/11-03-01-0003) — SAE framework connecting strategic, operational, assessment, and design aspects of aircraft cybersecurity.
- [Towards Secure Air Traffic Surveillance: A Survey on ADS-B Threats, Existing Solutions, and Future Research](https://doi.org/10.1109/OJCS.2026.3651384) — Recent 2026 review of ADS-B security, including spoofing, injection, modification, and jamming threats.
- [Research Directions on Cybersecurity in Civil Aviation — Literature Review](https://doi.org/10.55676/asi.v7i1.105) — 2026 literature review mapping civil-aviation cybersecurity research through 2025.
- [Aviation Cybersecurity Governance: Towards an Operational Framework for the Airport Domain](https://doi.org/10.3390/info17020177) — 2026 research on airport-domain cybersecurity governance.

## Airplane Challenges, Labs & Practical Research

- [Bricks in the Air](https://github.com/AerospaceVillage/BricksInTheAir) — Hands-on introductory aviation-security workshop using LEGO and Arduino-style components to model aircraft-bus concepts.
- [DDS at DEF CON](https://github.com/deptofdefense/dds-at-DEFCON) — Archived collection of Department of Defense Digital Service aerospace workshops and build material.
- [Aerospace Village](https://www.aerospacevillage.org/) — Community-led aerospace cybersecurity talks, workshops, CTFs, and research activities.
- [OpenSky Network](https://opensky-network.org/) — Research platform for ADS-B/Mode-S data and large-scale aircraft observation.
- [Mode-S.org](https://mode-s.org/) — Technical learning resource covering ADS-B, Mode-S, and aircraft surveillance data.
- [readsb](https://github.com/wiedehopf/readsb) — Modern ADS-B/Mode-S decoder for controlled RF reception and analysis.
- [dump1090](https://github.com/antirez/dump1090) — Classic RTL-SDR Mode-S/ADS-B decoder.
- [libacars](https://github.com/szpajder/libacars) — Decoder library for ACARS and related aviation datalink applications.
- [dumpvdl2](https://github.com/szpajder/dumpvdl2) — VDL Mode 2 decoder and analyzer.
- [dumphfdl](https://github.com/szpajder/dumphfdl) — HFDL decoder for aviation communications research.
- [JAERO](https://github.com/szpajder/JAERO) — Decoder for Aero/SATCOM signals carrying aircraft communications.

# Satellite Hacking

Satellite security is a **system-of-systems** problem. The attack
surface can include the spacecraft flight software, payload, radios,
command and telemetry protocols, ground stations, mission-control
software, cloud infrastructure, supply chain, and external dependencies
such as GNSS/PNT. NASA explicitly recommends treating the flight
platform, payloads, ground segment, and supporting services as part of
the security problem.

## Satellite Standards, Guidance & Security Frameworks

-   [NASA --- Space Security Best Practices
    Guide](https://www.nasa.gov/general/nasa-issues-new-space-security-best-practices-guide/)
    --- NASA's foundational public guide for cybersecurity of space
    missions.
-   [NASA --- Space Security Best Practices Guide
    PDF](https://swehb.nasa.gov/download/attachments/146540183/Space%20Security%20Best%20Practices%20Guide%20BPG%20REV%20B.pdf)
    --- Publicly released revision of the guide.
-   [NASA Small Spacecraft State of the Art --- Ground Data Systems &
    Mission
    Operations](https://www.nasa.gov/smallsat-institute/sst-soa/ground-data-systems-and-mission-operations/)
    --- Includes a dedicated cybersecurity section discussing command
    paths, ground systems, communications, GNSS/PNT dependencies, and
    mission-level risk.
-   [NIST IR 8270 --- Introduction to Cybersecurity for Commercial
    Satellite Operations](https://csrc.nist.gov/pubs/ir/8270/final) ---
    Excellent starting point for commercial satellite cybersecurity risk
    management.
-   [NIST IR 8401 --- Satellite Ground Segment: Applying the
    Cybersecurity Framework to Satellite Command and
    Control](https://csrc.nist.gov/pubs/ir/8401/final) --- Detailed
    framework application to satellite ground-segment command and
    control.
-   [NIST IR 8441 --- Cybersecurity Framework Profile for Hybrid
    Satellite Networks](https://csrc.nist.gov/pubs/ir/8441/final) ---
    Security framework for hybrid satellite networks spanning terminals,
    antennas, satellites, payloads, and other components.
-   [CCSDS Security Architecture for Space Data
    Systems](https://ccsds.org/Pubs/351x0m1.pdf) --- Foundational CCSDS
    security architecture for space data systems.
-   [CCSDS Green Books](https://ccsds.org/publications/greenbooks/) ---
    Informational reports, including security guidance and space-mission
    threat analysis.
-   [CCSDS Blue Books](https://ccsds.org/publications/bluebooks/) ---
    Normative space-data standards, including cryptographic algorithms
    and Space Data Link Security Protocol.
-   [CCSDS Security Working Group](https://ccsds.org/about/) --- CCSDS
    security work covering flight and ground mission resources.
-   [CCSDS Space Data Link Security
    Protocol](https://ccsds.org/Pubs/355x0b2.pdf) --- Standardized
    security mechanism for CCSDS data links.
-   [ECSS-E-ST-80C --- Security in Space Systems
    Lifecycles](https://ecss.nl/standard/ecss-e-st-80c-space-engineering-security-in-space-systems-lifecycles/)
    --- European space-engineering standard covering security across
    space, ground, launch, and support segments.
-   [IEEE 3536-2026 --- Space System Cybersecurity
    Design](https://standards.ieee.org/ieee/3536/11916/) --- Current
    IEEE standard for component-level cybersecure space-system design.
-   [ESA
    Cybersecurity](https://technology.esa.int/program/cybersecurity) ---
    ESA cybersecurity engineering and research program.
-   [ESA Cybersecurity
    Laboratory](https://technology.esa.int/lab/cybersecurity-laboratory)
    --- ESA laboratory for testing and demonstrating security
    technologies for space and ground systems.
-   [ESA Cyber
    Resilience](https://www.esa.int/About_Us/Cyber_resilience_at_ESA/How_ESA_ensures_cybersecurity_in_space)
    --- Overview of ESA's approach to space cybersecurity and cyber
    resilience.
-   [ESA Cyber Security Operations
    Centre](https://www.esa.int/Space_Safety/Cyber_resilience/ESA_inaugurates_new_Cyber_Security_Operations_Centre)
    --- ESA's operational cyber-monitoring capability for space and
    ground infrastructure.

## Satellite Threat Modeling & Adversary Knowledge

-   [SPARTA --- Space Attack Research & Tactic
    Analysis](https://sparta.aerospace.org/) --- Aerospace Corporation's
    dedicated space-system adversary behavior matrix.
-   [SPARTA User
    Guide](https://sparta.aerospace.org/resources/user-guide) ---
    Explains how to use SPARTA as a space-cyber threat knowledge base.
-   [SPACE-SHIELD](https://spaceshield.esa.int/) --- ESA's ATT&CK-like
    knowledge base for space-system threats and countermeasures.
-   [Awesome Space
    Security](https://github.com/Peco602/awesome-space-security) ---
    Existing curated collection of space-security papers, reports,
    directives, threat models, and tools.
-   [Space ISAC](https://spaceisac.org/) --- Industry
    information-sharing organization focused on threats,
    vulnerabilities, incidents, and resilience across the space sector.
-   [Space ISAC Resources](https://spaceisac.org/resources/) ---
    Collection of space-security papers and resources, including SPARTA
    and Aerospace Corporation work.
-   [EU Space
    ISAC](https://www.euspa.europa.eu/eu-space-programme/eu-space-and-security/eu-space-isac)
    --- European information-sharing initiative for space-security
    incidents, threats, vulnerabilities, and cyber trends.
-   [MITRE ATT&CK](https://attack.mitre.org/) --- General
    adversary-behavior framework useful when mapping ground-segment and
    enterprise threats.
-   [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)
    --- General risk-management framework that complements
    space-specific models.

## Satellite Ground Stations, SDR & Telemetry

-   [SatNOGS](https://satnogs.org/) --- Open satellite ground-station
    network and ecosystem.
-   [SatNOGS GitHub](https://github.com/satnogs) --- Open-source
    ground-station software and supporting projects.
-   [SatNOGS DB](https://db.satnogs.org/) --- Public satellite
    observation and telemetry database.
-   [Libre Space Foundation](https://libre.space/) --- Open-source space
    community behind projects including SatNOGS.
-   [gr-satellites](https://github.com/daniestevez/gr-satellites) ---
    GNU Radio-based telemetry decoders for many amateur satellites,
    including CCSDS-related protocols.
-   [GNU Radio](https://github.com/gnuradio/gnuradio) --- Core SDR
    framework for satellite signal analysis and experimentation.
-   [GNU Radio
    Companion](https://wiki.gnuradio.org/index.php/GNURadioCompanion)
    --- Visual environment for building GNU Radio signal-processing
    flowgraphs.
-   [SatDump](https://github.com/SatDump/SatDump) --- Open-source
    satellite data processing and decoding software supporting a wide
    variety of signals and missions.
-   [GPredict](https://github.com/csete/gpredict) --- Satellite tracking
    and pass-prediction software.
-   [Skyfield](https://github.com/skyfielders/python-skyfield) ---
    Python astronomy/orbital mechanics library useful for satellite
    tracking research.
-   [CelesTrak](https://celestrak.org/) --- Public orbital-element and
    satellite-tracking data source.
-   [pyorbital](https://github.com/pytroll/pyorbital) --- Python library
    for satellite orbital calculations and geolocation.
-   [Inspectrum](https://github.com/miek/inspectrum) --- RF-signal
    inspection tool useful for recorded satellite signals.
-   [Universal Radio Hacker](https://github.com/jopohl/urh) ---
    Protocol-analysis and reverse-engineering tool for recorded RF
    signals.
-   [SDR++](https://github.com/AlexandreRouma/SDRPlusPlus) ---
    Cross-platform SDR application useful for signal discovery and
    analysis.
-   [SoapySDR](https://github.com/pothosware/SoapySDR) ---
    Hardware-independent SDR abstraction layer.
-   [gr-satnogs](https://gitlab.com/librespacefoundation/gr-satnogs) ---
    GNU Radio components used by the SatNOGS ecosystem.

## Satellite Flight Software & Space Systems

-   [NASA core Flight System (cFS)](https://github.com/nasa/cFS) ---
    Open-source flight-software framework used across NASA missions and
    useful for security research in a realistic flight-software
    environment.
-   [NASA F´ (F Prime)](https://github.com/nasa/fprime) --- Open-source
    flight-software framework developed at JPL.
-   [NASA NOS3](https://github.com/nasa/nos3) --- NASA Operational
    Simulator for Small Satellites; useful for exercising flight
    software without launching hardware.
-   [OpenSatKit](https://github.com/OpenSatKit/OpenSatKit) ---
    Open-source framework and training environment built around NASA
    cFS.
-   [cFS Security](https://github.com/nasa/cFS) --- Start from the cFS
    security model, issue tracker, and secure-development practices when
    researching flight software.
-   [OreSat](https://github.com/oresat) --- Open-source CubeSat
    ecosystem providing accessible spacecraft hardware/software
    projects.
-   [Libre Space Foundation](https://github.com/Libre-Space-Foundation)
    --- Open-source satellite and ground-segment projects.
-   [CCSDS](https://github.com/CCSDS.org) --- Reference point for space
    communication standards and protocol definitions.

## Satellite Research & Datasets

-   [NASA Technical Reports Server](https://ntrs.nasa.gov/) ---
    Searchable archive of NASA technical reports and research papers.
-   [NASA Space Communications and
    Navigation](https://www.nasa.gov/space-communications-navigation/)
    --- Primary material on space communications, navigation, and
    related technologies.
-   [ESA
    Library](https://www.esa.int/Enabling_Support/Space_Engineering_Technology)
    --- ESA technical and engineering resources.
-   [NIST CSRC](https://csrc.nist.gov/) --- Cybersecurity research and
    standards relevant to satellite ground segments and space
    infrastructure.
-   [CCSDS Publications](https://ccsds.org/publications/) ---
    Authoritative source for space-data-system standards and technical
    reports.
-   [ECSS Standards](https://ecss.nl/standards/) --- European
    space-engineering standards, including security engineering.
-   [Space-Track](https://www.space-track.org/) --- Official U.S.
    government source for space-object tracking data; account and access
    restrictions apply.
-   [CelesTrak](https://celestrak.org/) --- Public orbital data and
    space-object information.
-   [SatNOGS DB](https://db.satnogs.org/) --- Open observations and
    telemetry data from the global SatNOGS network.
-   [OPENSAT](https://github.com/Satellite-OSS) --- Open-source
    satellite community collecting papers, datasets, tools, and runnable
    spacecraft software.
-   [Space ISAC](https://spaceisac.org/) --- Community and industry
    source for space-sector cyber threat intelligence and resilience
    material.

------------------------------------------------------------------------

## Contributing

A good contribution should be:

1.  **Relevant** to drone, aircraft, or satellite cybersecurity.
2.  **Useful** to researchers, engineers, students, or defenders.
3.  **Verifiable** --- preferably an official source, peer-reviewed
    paper, recognized research organization, or established open-source
    project.
4.  **Maintained** --- avoid abandoned repositories unless they have
    lasting historical or educational value.
5.  **Clearly described** --- explain what the resource is and why it
    belongs here.
6.  **Safe to publish** --- this list is for legitimate research and
    education, not operational compromise of real aircraft, drones,
    satellites, or aviation infrastructure.

When adding a resource, prefer the **canonical upstream URL** over
mirrors, personal blogs, link aggregators, or scraped copies.

## A Note on "Hacking"

In this list, *hacking* means security research: understanding
architectures, reverse engineering, protocol analysis, fuzzing, threat
modeling, vulnerability research, detection, and controlled
experimentation.

For safety-critical aerospace systems, prefer **SITL/simulation,
recorded RF, isolated hardware labs, emulators, test ranges, and
intentionally vulnerable systems** over live operational systems.


## Satellite Conference Talks & Videos

### Aerospace Village / DEF CON

- [DEF CON 28 — Exploiting Spacecraft](https://www.youtube.com/watch?v=b8QWNiqTx1c) — Practical spacecraft-security research presented in the Aerospace Village.
- [DEF CON 29 — Unboxing the Spacecraft Software BlackBox: Hunting for Vulnerabilities](https://www.youtube.com/watch?v=WvKtdXSRvhM) — Firmware/flight-software oriented research.
- [DEF CON 30 — Hunting for Spacecraft Zero Days Using Digital Twins](https://www.youtube.com/watch?v=t_efCpd2PbM) — Digital-twin driven vulnerability research.
- [DEF CON 30 — Hack-A-Sat 3](https://www.youtube.com/watch?v=NYq1mGi8d4U) — Overview of the Hack-A-Sat series, challenges, and Moonlighter.
- [SPARTA — DEF CON Presentation Collection](https://sparta.aerospace.org/resources/OTR202500882-DefCon2025-Hacking_Space_to_Defend_It_1.pdf) — Aerospace's 2025 resource pack linking the DEF CON SPARTA presentation series, including 2020–2024 material.
- [DEF CON 32 Aerospace Village Schedule](https://www.defcon.outel.org/defcon32/dc32-consolidated_page_split_Vil.html) — Includes Space Systems Security CTF, Hack-A-Sat Digital Twin, satellite-security talks, and practical workshops.
- [STARPWN](https://starpwn.ctfd.io/) — Aerospace Village's DEF CON 34 space-security CTF platform; the site also exposes a practice environment.
- [STARPWN 2026 Write-ups](https://github.com/JonghoMoon/STARPWN-2026-Writeup) — Public write-ups and reproducible analyses for the 2026 challenge set.

### Black Hat / SATCOM / RF

- [Satellite Hacking for Fun and Profit — Black Hat DC 2009](https://www.youtube.com/watch?v=PyXZX63etog) — Classic satellite-hacking presentation.
- [SATCOM Terminals: Hacking by Air, Sea, and Land — Black Hat USA 2014](https://www.youtube.com/watch?v=YeKswEamOl4) — SATCOM-terminal security research.
- [Spread Spectrum Satcom Hacking — Black Hat USA 2015](https://www.youtube.com/watch?v=arPqhHQ-R4o) — Globalstar simplex-data research.
- [Whispers Among the Stars — Black Hat USA 2020](https://www.youtube.com/watch?v=d5Sbwlu6f8o) — Practical satellite-eavesdropping research.
- [Iridium Satellite Hacking — HOPE XI](https://www.youtube.com/watch?v=cvKaC4pNvck) — RF and satellite-network reverse engineering.
- [Reverse Engineering Outernet — 33C3](https://www.youtube.com/watch?v=TCoSRx7DpGY) — Satellite IP/content-distribution reverse engineering.
- [Reverse Engineering Satellite-Based IP Content Distribution — ReCon Brussels](https://www.youtube.com/watch?v=U1WyBP4lKZk) — SATCOM protocol and service research.
- [Reverse Engineering NOAA and ARGOS Satellite](https://www.youtube.com/watch?v=HjBMxoHTjCk) — Satellite signal and protocol reverse engineering.
- [Satellite Communications Reverse Engineering — H2HC](https://www.youtube.com/watch?v=SIxRyVKlpEo) — Lucas Teske's practical SATCOM work.
- [GPS as an Attack Vector — S4 Conference](https://www.youtube.com/watch?v=Duxr1yRKRoU) — GNSS/PNT security research.
- [GNSS Hacking, From Satellite Signals to Hardware/Software Cybersecurity](https://www.youtube.com/watch?v=Au43CmiOO_g) — GNSS security from RF through embedded software.
- [CYSAT 2023](https://www.youtube.com/watch?v=l9nezXxO3iE) — Space cybersecurity conference material referenced by SPARTA.
- [CYSAT 2024](https://www.youtube.com/watch?v=jtMFI1DpAFo) — More recent space-cyber content referenced by SPARTA.

## Hack-A-Sat & Space CTFs

Hack-A-Sat is one of the strongest practical learning resources in this field because the organizers have publicly released challenge artifacts, technical papers, solver material, and in several years the underlying software and hardware used by the competition.

- [Hack-A-Sat Resource Library](https://github.com/deptofdefense/hack-a-sat-library) — Archived resource collection with articles, talks, books, tools, videos, and qualifier material.
- [Hack-A-Sat 2 — 2021 Final](https://github.com/cromulencellc/hackasat-final-2021) — Public release with challenge source, solutions, flatsat software/tools, custom hardware code, cFS, and COSMOS deployments.
- [Hack-A-Sat 3 — 2022 Qualifier](https://github.com/cromulencellc/hackasat-qualifier-2022) — Public challenge source, solutions, build infrastructure, and solver notes.
- [Hack-A-Sat 3 — 2022 Final](https://github.com/cromulencellc/hackasat-finals-2022) — Ground and satellite challenges, solvers, user guide, and team write-ups.
- [Hack-A-Sat 3 Qualifier Technical Papers](https://github.com/cromulencellc/hackasat-qualifier-2022-techpapers) — Technical write-ups from top-performing teams.
- [Hack-A-Sat 4 — 2023 Qualifier](https://github.com/cromulencellc/hackasat-qualifier-2023) — Public challenge source, solutions, infrastructure, and notes.
- [Hack-A-Sat 4 — 2023 Final](https://github.com/cromulencellc/hackasat-finals-2023) — Final challenges, solutions, write-ups, and public game data.
- [P4 Team CTF Write-ups](https://github.com/p4-team/ctf) — Includes Hack-A-Sat 4 qualifier write-ups alongside other high-level CTF material.
- [STARPWN 2026 Write-ups](https://github.com/JonghoMoon/STARPWN-2026-Writeup) — 2026 challenge analyses across communication/RF, ground operations, forensics, space operations, and related categories.
- [STARPWN Platform](https://starpwn.ctfd.io/) — Current Aerospace Village CTF platform and practice environment.
- [Hack-A-Sat at AFRL](https://www.afresearchlab.com/hack-a-sat/) — Official program background and history.

## Satellite Recent Research

- [Awesome Satellite Networking](https://github.com/liuwei-network/awesome-satellite-network) — Especially valuable companion collection: 188 peer-reviewed papers, 16 projects, 12 tools, and 28 datasets, including recent 2025–2026 work on security, measurement, physical layer, ground segment, and experimental platforms.
- [SaTor: Exploring Satellite Routing in Tor to Reduce Latency](https://github.com/liuwei-network/awesome-satellite-network) — Listed in the 2026 IEEE S&P research section of Awesome Satellite Networking.
- [SERENADE: A Digital Twin Emulator for LEO Satellite Networking At-Scale](https://github.com/liuwei-network/awesome-satellite-network) — 2026 experimental-platform research highlighted by the collection.
- [A Variegated Look at Direct-to-Cell Satellites in the Wild](https://github.com/liuwei-network/awesome-satellite-network) — Recent measurement work on direct-to-cell systems.
- [Cyber Attacks on Space Information Networks: Vulnerabilities, Threats, and Countermeasures for Satellite Security](https://doi.org/10.3390/jcp5030076) — 2025 review of satellite information-network threats and defenses.
- [Space Cybersecurity Challenges, Mitigation Techniques, Anticipated Readiness, and Future Directions](https://doi.org/10.1016/j.ijcip.2024.100724) — Open-access review of the space-cybersecurity landscape.
- [CubeSat Security Attack Tree Analysis](https://doi.org/10.1109/SMC-IT51442.2021.00016) — Attack-tree methodology applied to CubeSat architectures.
- [ATM: A Logic for Quantitative Security Properties on Attack Trees](https://doi.org/10.1007/s10270-025-01323-z) — Research that includes a CubeSat case study and formal security reasoning over attack trees.
- [Security Assessment of Internet-Exposed Satellite Ground Segments via Non-Intrusive Reconnaissance](https://doi.org/10.23386/joss.2026.3.1.006) — Recent 2026 research on the externally reachable ground-segment attack surface.
- [Cybersecurity Risks in Satellite Ground-Segment Infrastructure: Threat Profiling and Analysis](https://www.irejournals.com/paper-details/1722886) — 2026 ground-segment risk profiling study.


------------------------------------------------------------------------

## Recommended Starting Paths

### New to Drone Security

`MAVLink → PX4/ArduPilot SITL → QGroundControl → Wireshark → MAVLink security → fuzzing → RF/SDR`

### New to Aircraft Security

`ADS-B/Mode-S → RTL-SDR → dump1090/readsb → OpenSky → ACARS/VDL2 → aviation cybersecurity standards → avionics architecture`

### New to Satellite Security

`Satellite fundamentals → SatNOGS → SDR → gr-satellites/SatDump → CCSDS → NASA/NIST guidance → SPARTA/SPACE-SHIELD → flight software`

------------------------------------------------------------------------


## Reference Curations & Source Repositories

This list was expanded by cross-checking and consolidating material from existing aerospace-security collections. These repositories are **sources and companions**, not a replacement for the primary sources linked throughout this list.

### Drone Security

- [dronesploit/awesome-drone-hacking](https://github.com/dronesploit/awesome-drone-hacking) — Earlier curated list covering drone-hacking literature and tools.
- [nicholasaleks/Awesome-Drone-Hacking](https://github.com/nicholasaleks/Awesome-Drone-Hacking) — Large modern collection spanning labs/CTFs, talks/videos, RTOS, flight controllers, RF, telemetry, firmware, GCS, vendor research, CVEs, disclosure programs, and training.

### Aviation Security

- [deptofdefense/hack-aviation-library](https://github.com/deptofdefense/hack-aviation-library) — Archived U.S. Defense Digital Service learning library covering websites, articles, tools, videos, books, programming libraries, and practical aviation-security workshops.
- [deptofdefense/dds-at-DEFCON](https://github.com/deptofdefense/dds-at-DEFCON) — Archived DDS workshop repository with aviation and space activities from DEF CON 27 through DEF CON 32.
- [Aerospace Village](https://github.com/AerospaceVillage) — Community repository ecosystem for aerospace-security research, workshops, and open-source projects.

### Space / Satellite Security

- [Peco602/awesome-space-security](https://github.com/Peco602/awesome-space-security) — Dedicated Awesome List organized into books, directives, papers, reports, talks, threat modeling, and tools.
- [liuwei-network/awesome-satellite-network](https://github.com/liuwei-network/awesome-satellite-network) — Large academic/networking collection covering papers, open-source systems, datasets, testbeds, tools, and satellite/NTN research.
- [deptofdefense/hack-a-sat-library](https://github.com/deptofdefense/hack-a-sat-library) — Archived Hack-A-Sat resource library with videos, reports, books, tools, workshops, and challenge material.
- [cromulencellc/hackasat-final-2021](https://github.com/cromulencellc/hackasat-final-2021) — Public Hack-A-Sat 2 final release.
- [cromulencellc/hackasat-qualifier-2022](https://github.com/cromulencellc/hackasat-qualifier-2022) — Public Hack-A-Sat 3 qualifier release.
- [cromulencellc/hackasat-finals-2022](https://github.com/cromulencellc/hackasat-finals-2022) — Public Hack-A-Sat 3 final release.
- [cromulencellc/hackasat-qualifier-2022-techpapers](https://github.com/cromulencellc/hackasat-qualifier-2022-techpapers) — Public technical papers from Hack-A-Sat 3 qualifier teams.
- [cromulencellc/hackasat-qualifier-2023](https://github.com/cromulencellc/hackasat-qualifier-2023) — Public Hack-A-Sat 4 qualifier release.
- [cromulencellc/hackasat-finals-2023](https://github.com/cromulencellc/hackasat-finals-2023) — Public Hack-A-Sat 4 final release.
- [AXRoux/hack-satellites](https://github.com/AXRoux/hack-satellites) — Another public satellite-hacking resource library derived from the Hack-A-Sat ecosystem.
- [JonghoMoon/STARPWN-2026-Writeup](https://github.com/JonghoMoon/STARPWN-2026-Writeup) — Recent 2026 public write-ups and reproducible analyses from STARPWN.

### Why These Sources Matter

The intent is to combine several different kinds of curation:

- **Awesome Lists** for breadth and discovery.
- **Government / standards bodies** for authoritative guidance.
- **Peer-reviewed research** for technical depth.
- **CTF releases and write-ups** for practical, reproducible labs.
- **Conference talks and videos** for demonstrations and historical context.
- **Open-source flight/ground software** for realistic research environments.

> A source repository being listed here does not mean every individual link in it is still current or authoritative. Always prefer the canonical upstream source and check the date, maintenance status, and scope before relying on a resource.


### Cross-Domain Aerospace Security

- [SPARTA](https://sparta.aerospace.org/) — Space-system adversary tactics and techniques.
- [SPACE-SHIELD](https://spaceshield.esa.int/) — ESA space-security threat and countermeasure knowledge base.
- [Aerospace Village](https://www.aerospacevillage.org/) — Community spanning airports, aviation, drones, aircraft, satellites, and space operations.
- [CISA](https://www.cisa.gov/) — Cross-sector cybersecurity guidance and advisories.
- [NIST](https://csrc.nist.gov/) — Cybersecurity standards, frameworks, and technical publications.
- [OWASP](https://owasp.org/) — Application and embedded-security methodologies applicable to GCS, mobile apps, cloud backends, and companion systems.
- [GNU Radio](https://www.gnuradio.org/) — Common SDR foundation across UAV, aircraft, and satellite RF research.
- [Universal Radio Hacker](https://github.com/jopohl/urh) — Protocol analysis of recorded RF signals in authorized environments.
- [Wireshark](https://www.wireshark.org/) — Network/protocol analysis across GCS, ground stations, avionics labs, and satellite infrastructures.
- [QEMU](https://www.qemu.org/) — Emulation platform useful for embedded and flight-software research.
- [Renode](https://renode.io/) — Embedded-system simulation and emulation platform.
- [OSS-Fuzz](https://github.com/google/oss-fuzz) — Large-scale fuzzing infrastructure whose techniques can be adapted to aerospace protocol and firmware parsers.

## Further Reading

For a broader security-engineering foundation, combine the
aerospace-specific material above with:

-   [NIST Cybersecurity Framework](https://www.nist.gov/cyberframework)
-   [NIST Secure Software Development
    Framework](https://csrc.nist.gov/projects/ssdf)
-   [MITRE ATT&CK](https://attack.mitre.org/)
-   [OWASP](https://owasp.org/)
-   [CISA](https://www.cisa.gov/)
-   [FIRST](https://www.first.org/)
-   [CVE](https://www.cve.org/)
-   [CWE](https://cwe.mitre.org/)
-   [Google OSS-Fuzz](https://github.com/google/oss-fuzz)

> **Quality over quantity:** an Awesome List is most useful when every
> link earns its place. Prefer a smaller set of authoritative,
> maintained, technically meaningful resources over a large collection
> of questionable repositories.
