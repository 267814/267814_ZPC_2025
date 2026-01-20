---
title: "AxisCore Gimbal" 
layout: "mainproject" 
date: 2025-02-15 
draft: false
subtitle: "3-Axis Camera Stabilization System"
---

{{< img-text title="Concept & Vision" >}}
AxisCore started as an ambitious experiment to build a fully functional 3-axis camera stabilizer using only 3D printing and off-the-shelf electronics. The entire system is modular, allowing easy part replacement and upgrades. Powered by three brushless motors controlled by a Storm32 BGC board, it's designed specifically for smartphone stabilization.
{{< /img-text >}}

{{< stats-counter >}}

{{< chapter title="Meet AxisCore" subtitle="The Complete System" >}}

{{< 3d-model-main title="Complete Gimbal Assembly" src="models/full-assembly.glb" >}}
A fully functional 3-axis gimbal built entirely from 3D printed components. Rotate the model to explore every detail. All components are engineered for maximum strength at minimum weight.
{{< /3d-model-main >}}

{{< tech-specs >}}

{{< chapter title="Design Journey" subtitle="From Sketch to Reality" >}}

<div class="grid grid-cols-1 md:grid-cols-3 gap-6 mb-24 w-full">

{{< interactive-card
title="Initial Design"
image="images/1st-prot.png"
full_image="images/1st-prot-sketch.jpg"
desc="Finding the optimal form."
full_desc="Finding the optimal shape for weight distribution and ergonomic grip design. The first sketches were rough, but they established the fundamental 'L-shaped' load-bearing structure typical for one-handed gimbals. The goal was to minimize screw joints and create the simplest possible mechanical assembly."
>}}

{{< interactive-card
title="Concept Refinement"
image="images/2nd-prot.png"
full_image="images/2nd-prot-sketch.jpg"
desc="Gear train development."
full_desc="Detailed breakdown of the motor mounting system. This is where I tackled the biggest challenge – transferring motor torque to the arms without any backlash. Eventually, I chose direct drive for the Pitch and Roll axes, and belt drive for the Yaw axis. Each bearing is precisely positioned for minimal friction."
>}}

{{< interactive-card
title="Final Design"
image="images/3rd-prot.png"
full_image="images/3rd-prot-sketch.jpg"
desc="Aesthetic refinement."
full_desc="The final iteration of AxisCore. Features an integrated display in the handle and a joystick for camera control. The red accents aren't just decorative – they mark key moving parts and locking mechanisms for camera balancing. The design went through several iterations to improve ergonomics."
>}}

</div>

{{< chapter title="Component Breakdown" subtitle="Engineering Excellence" >}}

{{< component-3d 
title="Main Body (Body Top)"
category="STRUCTURE"
src="models/body-top.glb"
weight="145g"
material="PETG"
photos="images/body-top-1.jpg, images/body-top-2.jpg, images/body-top-3.jpg"
>}}
The upper section of the gimbal's main frame serves as the central mounting hub for critical electronics. This component bears the highest mechanical loads and contains mounting points for all three axes. **The structure uses topology optimization** – material is only placed where it's actually needed.

**Primary functions:**
- **Storm32 BGC board mounting** - Secure housing for the main controller
- **Joystick integration** - Ergonomic position for thumb control
- **Control buttons** - Additional input controls for mode switching
- **Battery compartment** - Houses the LiPo battery within the handle
- **Cable management** - Internal routing for clean wire organization

The part is printed from PETG for optimal strength-to-weight ratio. Precise bearing tolerances are critical – even a 0.1mm deviation causes mechanical play that affects stabilization quality.
{{< /component-3d >}}

{{< component-3d 
title="Bottom Cover (Body Bottom)" 
src="models/body-bottom.glb"
photos="images/bottom-1.jpg, images/bottom-2.jpg, images/bottom-3.jpg"
weight="98g"
material="PETG"
category="Structure"
reverse="true"
>}}
The lower body section serves primarily as **quick-access battery compartment**. Its design prioritizes easy battery swapping for extended shooting sessions without tools.

**Key features:**
- **Quick-release battery access** - Swap batteries in seconds
- **Ventilation slots** - Motor cooling during intensive use
- **Future expansion ready** - Space reserved for USB-C connector for charging
- **Integrated cable channels** - Clean wire routing to electronics above
- **Secure locking mechanism** - Quick-release screws for tool-free assembly

The modular design means you can access the battery without disassembling the entire gimbal - critical for field work when you need to swap power sources quickly.
{{< /component-3d >}}

{{< component-3d 
title="Y+X Axis Arm" 
src="models/arm-Y+X-axis.glb"
photos="images/arm-yx-1.jpg, images/arm-yx-2.jpg, images/arm-yx-3.jpg"
weight="82g"
material="PETG"
category="Mechanical"
>}}
Critical dual-axis component responsible for **gimbal rotation** and **camera tilt control**. This arm handles two distinct movements:

**Rotation functions:**
- **Pan axis (Y)** - Rotates the entire gimbal left and right
- **Tilt axis (X)** - Controls camera pitch up and down
- **Synchronized movement** - Both axes work together for smooth tracking

Needs to be **extremely rigid yet lightweight** – every extra gram means higher motor load. Printed from **PETG** for excellent strength-to-weight ratio and flexibility that helps absorb vibrations.

The arm features **precision-machined grooves** for the quick-release camera system. Thanks to the asymmetric design, the camera can be balanced in seconds without tools - critical for fast setup in the field.
{{< /component-3d >}}

{{< component-3d 
title="Z Axis Arm" 
src="models/arm-Z-axis.glb"
photos="images/arm-z-1.jpg, images/arm-z-2.jpg, images/arm-z-3.jpg"
weight="75g"
material="PETG"
category="Mechanical"
reverse="true"
>}}
The vertical arm handles the **roll axis (Z)** - responsible for keeping the phone level and enabling **portrait/landscape rotation**. This is the axis that makes horizon leveling possible.

**Primary functions:**
- **Horizon stabilization** - Keeps phone perfectly level
- **Portrait mode** - 90° rotation for vertical video
- **Landscape mode** - Standard horizontal orientation
- **Dynamic roll compensation** - Counteracts tilting movements

The design **minimizes moment of inertia**, enabling faster stabilization response. Lower rotational mass means the motor can react quicker to disturbances, resulting in smoother footage.

Features **integrated cable routing** for camera connection. The design is optimized to withstand the loads required for smartphone stabilization while weighing just 75 grams - every gram saved improves motor efficiency and battery life.
{{< /component-3d >}}

{{< component-3d 
title="Control PCB" 
src="models/PCB.glb"
photos="images/pcb-1.jpg, images/pcb-2.jpg, images/pcb-3.jpg"
weight="35g"
material="FR4 + SMD"
category="Electronics"
>}}
**Storm32 BGC (Brushless Gimbal Controller)** - the brain orchestrating all three axes. This specialized controller is designed specifically for gimbal applications, offering superior performance over generic flight controllers.

**Technical specifications:**
- **32-bit STM32 processor** - High-speed computation for real-time stabilization
- **1000Hz PID loop** - Updates motor positions 1000 times per second
- **3-axis control** - Simultaneous management of all three brushless motors
- **MPU6050 IMU sensor** - 6 degrees of freedom (3-axis accelerometer + 3-axis gyroscope)
- **0.01° precision** - Measures orientation changes with extreme accuracy
- **SMD components** - Surface-mount technology for minimal footprint

The Storm32 runs advanced **Field Oriented Control (FOC)** algorithms, enabling smooth, precise motor movements without the cogging typically associated with brushless motors. The onboard IMU constantly monitors orientation and sends correction signals to motors faster than mechanical systems could ever respond.

**Software features:**
- Auto-calibration routines
- PID auto-tuning
- Multiple operation modes
- USB configuration interface
{{< /component-3d >}}

{{< component-3d 
title="Joystick" 
src="models/joystick.glb"
photos="images/joystick-1.jpg, images/joystick-2.jpg, images/joystick-3.jpg"
weight="12g"
material="ABS"
category="Control"
reverse="true"
>}}
Analog joystick for manual camera positioning control. Enables **smooth movements** unlike digital buttons.

Uses a **Hall-effect sensor**, which has no mechanical contact wear. The joystick is positioned ergonomically where the thumb naturally rests, without requiring grip adjustment.
{{< /component-3d >}}

{{< component-3d 
title="Phone Holder" 
src="models/phoneholder.glb"
photos="images/phoneholder-1.jpg, images/phoneholder-2.jpg, images/phoneholder-3.jpg"
weight="45g"
material="TPU"
category="Accessory"
>}}
Universal smartphone mount with **integrated MagSafe magnets** for iPhone compatibility. This isn't just a simple clamp - it's an intelligent mounting system with embedded sensors.

**Key innovations:**
- **MagSafe magnetic array** - Instant iPhone attachment without clips
- **Integrated IMU sensor** - Gyroscope mounted directly on the phone holder
- **Universal compatibility** - Fits phones from 4.7" to 6.7" diagonal
- **TPU construction** - Flexible filament absorbs shocks and protects phone
- **Rubber padding** - Prevents scratches while ensuring secure grip

**Why put the IMU on the phone holder?**

By mounting the gyroscope directly where the phone sits, the system can measure **actual phone orientation** rather than gimbal orientation. This eliminates measurement errors from mechanical flex in the arms - the sensor reads exactly what the camera sees.

The MagSafe magnets provide ~1kg of holding force, enough to securely mount an iPhone even during rapid movements, while still allowing instant one-handed attachment and removal.
{{< /component-3d >}}

{{< component-3d 
title="Shaft" 
src="models/shaft-1.glb"
photos="images/shaft-1.jpg, images/shaft-2.jpg, images/shaft-3.jpg"
weight="18g"
material="Steel"
category="Mechanical"
reverse="true"
>}}
Precision-ground steel shaft serving dual critical functions: **magnetic arm mounting** and **torque transmission** from motors to arms.

**Design features:**
- **Magnetic mounting system** - Holds arms in place via embedded magnets
- **Tool-free assembly** - Arms snap on/off magnetically for quick setup
- **Torque transmission** - Transfers motor power to rotate arms
- **CNC machined** from stainless steel for zero backlash
- **608ZZ ball bearings** - Smooth, silent rotation
- **±0.01mm tolerance** - Critical for eliminating vibrations

**Why magnets instead of screws?**

Magnetic mounting enables **tool-free assembly/disassembly** in seconds. This is crucial for:
- Quick arm swaps for different configurations
- Easy maintenance and cleaning
- Portable setup without carrying tools
- No risk of losing tiny screws in the field

The magnetic force (combined with bearing friction) is strong enough to hold the arms firmly during operation, while still allowing intentional removal. The shaft itself is the mechanical connection point where motor rotation becomes gimbal movement - precision here is non-negotiable.
{{< /component-3d >}}

{{< component-3d 
title="Brushless Motor" 
src="models/motor-1.glb"
photos="images/motor-1.jpg, images/motor-2.jpg, images/motor-3.jpg"
weight="55g"
material="Copper + NdFeB"
category="Electronics"
>}}
Each motor has **14 poles** and can generate sufficient torque even at low RPM. Uses a **direct drive** system without gears to eliminate backlash.

Motors are controlled using **FOC (Field Oriented Control)** algorithm, enabling precise torque and position control. Each motor has dedicated **hall-effect sensors** for rotor position detection with 0.1° resolution.
{{< /component-3d >}}

{{< chapter title="The Journey" subtitle="Behind the Scenes" >}}

{{< dev-journal-wrapper 
    title="Development Journal"
    subtitle="A year of trial, error, and triumph"
>}}

{{< dev-journal
    date="Q1 2024"
    title="Chapter 1: The Idea"
    subtitle="How it all started"
    hours="30"
    iterations="6"
    stat1_label="Time Invested"
    stat1_value="30 hours"
    stat2_label="CAD Iterations"
    stat2_value="6"
    problem="My original idea was to build a self-leveling stabilization platform that could sit on a table or uneven surface. This evolved into a tripod concept, and finally into a handheld gimbal. But how to make it work with basic soldering skills and SolidWorks knowledge?"
    solution="After research, I discovered brushless motors and the Storm32 BGC controller. Though more expensive and complex than servos, they're smaller, lighter, and use electromagnetic control via gyroscope and accelerometer – no mechanical linkages means no wear."
    lesson="Start simple. The first designs were overly complicated – the final design is significantly simpler than the initial concept. Sometimes the right components make all the difference."
    expanded="true"
>}}

The journey started with a different goal entirely. My original vision was a **self-leveling stabilization station** – something you could place on a table or uneven surface that would automatically level itself. Pretty cool, right?

That concept evolved into a **tripod design**, but I kept thinking about portability. Eventually, I settled on building a **handheld gimbal**. The challenge? Making it DIY-friendly with just basic soldering skills and CAD modeling in SolidWorks.

### Early design decisions:

Initially, I planned to use an **Arduino Nano with servo motors**. Simple, cheap, and easy to program. But there was a problem – the servos I needed were **too large and heavy**. The whole gimbal would become top-heavy and unbalanced.

That's when I discovered **brushless motors**. 

### Why brushless motors changed everything:

- ⚙️ **Circular and compact** - much better for mounting
- 🔇 **No mechanical linkages** - controlled purely electromagnetically
- 📊 **Gyroscope + accelerometer control** - smooth, precise movements
- 💪 **No wear** - electromagnetic operation means no mechanical degradation

**The trade-off?** They're more expensive and don't work with Arduino. I needed a specialized controller.

### The Storm32 BGC solution:

I ordered everything from AliExpress:
- **Brushless motors:** ~350 CZK each (~$15)
- **Storm32 BGC board:** ~750 CZK (~$32)

Total investment in electronics: about $77. Not cheap for a DIY project, but worth it for the performance difference.

### CAD development:

I spent **minimum 4 days** just on the very first design in SolidWorks. Getting the motor mounts, bearing positions, and weight distribution right was crucial. 

For the first prototype alone, I redesigned the model **6 times**. Each iteration taught me something new about:
- Motor clearance requirements
- Cable routing paths
- Balance point calculations
- Structural weak points

By the end of Q1, I had a solid CAD model and all the electronics ordered. Time to start printing...

{{< /dev-journal >}}

{{< dev-journal
    date="Q2 2024"
    title="Chapter 2: 3D Printing Reality Check"
    subtitle="When prints don't cooperate"
    hours="50"
    fails="8"
    iterations="6"
    stat1_label="Failed Prints"
    stat1_value="8"
    stat2_label="Material Costs"
    stat2_value="~800 CZK"
    stat3_label="Prototypes Made"
    stat3_value="6"
    problem="Failed prints everywhere. Either the print quality was terrible, or I'd made a design error in the CAD model. Using 10-15% infill to speed up prints backfired – parts were too weak and kept failing."
    solution="Switched to PETG, which offers significantly better impact resistance and flexibility compared to PLA, while maintaining good strength properties for gimbal applications."
    lesson="Don't rush prints to save time. Low infill = weak parts. It's faster to print once properly than reprint failures multiple times."
>}}

With the CAD model ready and electronics ordered, it was time to start printing. **This is where reality hit hard.**

### The prototype evolution:

I went through **6 complete prototypes**, each testing different aspects:
- Size adjustments
- Shape refinements  
- Motor mount positions
- Weight distribution

### The printing nightmare:

My biggest challenges weren't just design issues – **the prints themselves kept failing**. I was trying to speed things up by using **10-15% infill**, thinking it would save time and material.

**Big mistake.**

Low infill meant:
- ❌ Parts were too weak
- ❌ Layers would separate under stress
- ❌ Motor vibrations caused cracks
- ❌ Screw threads would strip out

### Material testing journey:

**Failed attempts:**
1. ❌ **PLA with 10% infill** - Brittle and weak
2. ❌ **PLA with 15% infill** - Still not strong enough
3. ❌ **PLA+ with 15% infill** - Better but flexed too much

**Finally successful:**
4. ✅ **PETG with proper infill** - Perfect balance!

PETG proved ideal because:
- Flexible enough to absorb vibrations
- Strong enough to handle motor torques
- Better layer adhesion than PLA
- More impact resistant

### The cost of learning:

All those failed prints and material experiments added up:
- **~800 CZK** (~$35) in wasted filament
- **8 completely failed prints**
- **Countless hours** of printing time wasted

But each failure taught me something. By prototype #6, I finally had parts that didn't break during assembly.

### What I learned about 3D printing:

- **Infill matters** - Don't go below 30% for structural parts
- **Print orientation is critical** - Layer lines should run perpendicular to stress
- **Support placement** - Strategic supports prevent print failures
- **First layer adhesion** - If the first layer fails, the whole print fails

The material cost hurt, but it was cheaper than buying a commercial gimbal. And now I understood exactly why each part needed to be designed the way it was.

{{< /dev-journal >}}

{{< dev-journal
    date="Q3 2024"
    title="Chapter 3: Electronics Nightmare"
    subtitle="When you burn your only controller"
    hours="60"
    iterations="15"
    stat1_label="Waiting Time"
    stat1_value="4 weeks"
    stat2_label="Electronics Cost"
    stat2_value="~2,150 CZK"
    stat3_label="Coffee Consumed"
    stat3_value="Too many ☕"
    problem="Everything arrived from AliExpress perfectly. But then I hit a new wall – programming, control software, and worst of all... I had zero soldering experience. Then disaster: I fried my Storm32 board by getting the voltage wrong."
    solution="Ordered a second Storm32 board (another 750 CZK and 2 weeks waiting). Switched to battery power with proper voltage regulation. Had to buy battery, charger, and voltage regulator – another 650 CZK. But finally got everything working."
    lesson="Measure twice, connect once. One voltage mistake cost me 2 weeks and 750 CZK. Electronics don't forgive careless mistakes. Also: YouTube tutorials for soldering are worth their weight in gold."
>}}

Great news: everything from AliExpress arrived! The motors looked perfect, the Storm32 board was intact. I was excited to start connecting everything.

**Then reality hit – I didn't know how to solder.**

### Challenge #1: No electronics experience

I'd never:
- Soldered anything before
- Programmed a gimbal controller
- Worked with brushless motor drivers
- Debugged electronic circuits

Every connection was scary. "Is this wire gauge right?" "Did I get the polarity correct?" "Why is this getting hot?"

### Challenge #2: The disaster

I was connecting the power supply to the Storm32 board. I thought I had the voltage right. **I didn't.**

**Pop.** Smoke. The distinct smell of fried electronics.

I had just **killed my Storm32 board**.

### The expensive lesson:

Now I had to:
- ❌ Order a new Storm32 board: **750 CZK** (~$32)
- ⏳ Wait another **2 weeks** for shipping from China
- 😤 Deal with the frustration of my own mistake

**Total electronics casualties: 1,500 CZK just on Storm32 boards**

### Challenge #3: Power supply nightmare

I also needed to figure out power delivery. Options:
1. Wall adapter - Not portable ❌
2. USB power bank - Not enough current ❌  
3. LiPo battery - This could work! ✅

But batteries need:
- A proper charger: **~300 CZK**
- Voltage regulator: **~150 CZK**
- The battery itself: **~200 CZK**

**Another 650 CZK** (~$28) spent.

### The software struggle:

Getting the Storm32 software to actually work was its own battle:
- Installing drivers
- Configuring motor parameters
- Calibrating the IMU sensor
- Setting PID values (more on this later...)

YouTube tutorials and forum posts became my best friends. Spent **countless hours** just trying to get the motors to respond correctly.

### What I learned:

- 📺 **YouTube soldering tutorials** - Watched probably 20 videos
- ⚡ **Voltage is critical** - Always double-check with a multimeter
- 🔋 **Battery safety** - LiPo batteries are no joke, treat them with respect
- 💾 **Backup everything** - Config files, parameter values, everything

By the end of Q3, I had:
- ✅ Working Storm32 board (the second one)
- ✅ Proper power system with battery
- ✅ Software configured and running
- ✅ Motors responding to commands

**Total Q3 electronics cost: ~2,150 CZK** ($93) including the burned board.

Expensive lessons, but at least now I could actually start testing the gimbal mechanics.

{{< /dev-journal >}}

{{< dev-journal
    date="Q4 2024"
    title="Chapter 4: First Assembly"
    subtitle="Assembled but not yet working"
    hours="40"
    stat1_label="Assembly Attempts"
    stat1_value="6"
    stat2_label="Working Prototype"
    stat2_value="In Progress"
    stat3_label="Motor Response"
    stat3_value="✅ Working"
    problem="I have an assembled prototype, but it's not fully functional yet. For complete testing, I need the entire gimbal assembled. Due to failed prints, I haven't achieved that yet. But prototype #6 is showing the most promise."
    lesson="Progress isn't always linear. Even 'failures' teach you something. The motors respond to the board and provide resistance – that's already a huge win. Full balance testing requires the complete assembly."
>}}

After months of printing, failed electronics, and learning soldering, I finally have something that **looks like a gimbal**.

### Current status: Assembled but not functional

Prototype #6 is the best iteration so far:
- ✅ All structural parts fit together
- ✅ Motors are mounted correctly
- ✅ Electronics are connected
- ✅ No obvious design flaws

**But** – it's not fully functional yet.

### Why not fully tested?

To properly test gimbal stabilization, I need:
1. **Complete assembly** - All parts installed
2. **Balanced system** - Camera/phone mounted and balanced
3. **Calibrated IMU** - Sensors properly initialized
4. **Tuned PID** - Motors responding smoothly

Right now, I'm still at step 1-2. The failed prints from earlier months mean some parts aren't perfect, so full assembly is tricky.

### What IS working:

The motors respond to the Storm32 board! I can test basic functionality:

**Test 1: Motor power**
- ✅ Motors spin when commanded
- ✅ They provide resistance when moved manually
- ✅ No overheating issues

**Test 2: Board response**
- ✅ Storm32 communicates with motors
- ✅ IMU sensor reading orientation
- ✅ Software interface working

**What I CAN'T test yet:**
- ❌ Full 3-axis stabilization
- ❌ Balance with phone mounted
- ❌ Smooth video capture
- ❌ Battery life under load

### The challenge:

I need **all parts working together** to test actual stabilization. A partially assembled gimbal can't demonstrate balance. It's like testing a car engine without the transmission – sure it runs, but you can't drive it yet.

### Prototype #6 improvements:

Compared to earlier attempts:
- ✅ Better motor mounting (no wobble)
- ✅ Stronger arm connections
- ✅ Proper cable routing
- ✅ Improved weight distribution

The parts that DO work are working great. Now I just need to nail down those final failed prints and get everything assembled properly.

### Next steps:

1. **Reprint failed parts** with better settings
2. **Full assembly** with all components
3. **Balance testing** with phone mounted
4. **PID tuning** for smooth operation
5. **Real-world video tests**

I'm so close. The electronics work, the motors work, the design is sound. Now it's just about getting that last 10% right.

**Almost there...** 🔧

{{< /dev-journal >}}

{{< /dev-journal-wrapper >}}

{{< chapter title="What's Next?" subtitle="Future Upgrades" >}}

<div class="grid grid-cols-1 md:grid-cols-2 gap-6 mb-24">
<div class="bg-gradient-to-br from-[#2A2A2A] to-[#1a1a1a] border border-white/10 rounded-2xl p-8 hover:border-[#FF425C]/30 transition-all">
<h4 class="text-2xl font-bold text-white mb-4">🔋 Wireless Charging</h4>
<p class="text-gray-400">Implementation of Qi wireless charging to eliminate USB ports and improve water resistance.</p>
</div>

<div class="bg-gradient-to-br from-[#2A2A2A] to-[#1a1a1a] border border-white/10 rounded-2xl p-8 hover:border-[#FF425C]/30 transition-all">
<h4 class="text-2xl font-bold text-white mb-4">📱 Bluetooth App</h4>
<p class="text-gray-400">Mobile app for advanced PID parameter configuration and real-time telemetry monitoring.</p>
</div>

<div class="bg-gradient-to-br from-[#2A2A2A] to-[#1a1a1a] border border-white/10 rounded-2xl p-8 hover:border-[#FF425C]/30 transition-all">
<h4 class="text-2xl font-bold text-white mb-4">🎯 Object Tracking</h4>
<p class="text-gray-400">AI-powered object tracking using OpenCV with automatic target focus.</p>
</div>

<div class="bg-gradient-to-br from-[#2A2A2A] to-[#1a1a1a] border border-white/10 rounded-2xl p-8 hover:border-[#FF425C]/30 transition-all">
<h4 class="text-2xl font-bold text-white mb-4">⚡ Encoder Upgrade</h4>
<p class="text-gray-400">Transition from Hall sensors to AS5600 magnetic encoders for 12-bit position resolution.</p>
</div>
</div>