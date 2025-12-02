---
title: "Electronic Systems"
category: "Electronics & IoT"
image: "/images/featured/Elec.png"
layout: "project"
date: 2024-01-05
---

{{< img-text title="Intro" >}}
This section shows a project I built using Arduino and the Tinkercad simulator. My goal wasn't just to connect a few wires, but to build an interactive controller that has advanced feedback. I programmed it to use timers and logic to watch for "critical" situations, kind of like a safety system you'd find in a real machine.
{{< /img-text >}}

{{< img-text title="The Circuit" src="/images/Obvod.png" size="medium" >}}
Here’s how the circuit works. The Arduino Uno is the brain for everything. I use a potentiometer (the black knob) as the main input. The Arduino reads the position of the knob and does two things at once:

* It tells the servo motor to turn to that exact same angle.
* It lights up the LEDs to show what "zone" you're in. First just green, then green and amber, and finally all three including the red.

A key part of the design is the external battery pack. The servo motor needs more power than the Arduino can safely provide, so I gave it its own battery. I then had to connect the "ground" (GND) from the Arduino to the battery's ground. This is an essential step to make sure all the parts can "talk" to each other correctly.
{{< /img-text >}}

{{< img-text title="Real-World Application" >}}
AAs the video shows, this isn't just a random toy. It's a prototype for a real-world control system, like a control panel for an industrial motor or a furnace.

+ The Potentiometer: This is the main dial the operator uses to set the power level or temperature.

+ The Servo: This represents the actual motor or valve that's doing the physical work (like opening a fuel line or spinning a mixer).

+ The LEDs: These are the status lights showing the load. Green means "Idle," amber means "Working Load," and red means you're "redlining" at maximum power.

The most important feature is the 3-second safety timer. I programmed the Arduino to watch how long the system is in the red zone. If the operator pushes the system to its limit and leaves it there for more than 3 seconds, the red LED starts flashing. This is a serious alarm telling the operator, "EMERGENCY! Reduce the load now before something overheats or breaks!"
{{< /img-text >}}

{{< video src="/images/Funkce obvodu.mp4" size="small" >}}


{{< chapter title="The Code" subtitle="C++ Logic" >}}

<div class="max-w-4xl mx-auto bg-[#1e1e1e] p-6 rounded-2xl border border-white/10 shadow-2xl overflow-x-auto text-sm font-mono text-gray-300 leading-relaxed mb-24">
<pre><code>#include &lt;Servo.h&gt; 

Servo mojeServo;  

// --- Definice pinů ---
const int potenciometrPin = A0; 
const int servoPin = 9;         
const int ledZelenaPin = 12;
const int ledOranzovaPin = 11;
const int ledCervenaPin = 10;

// --- Proměnné pro časování ---
unsigned long casVstupuDoCervene = 0; 
const long limitAlarmu = 3000; // 3 sekundy

unsigned long casPoslednihoBliknuti = 0; 
bool stavBlikaniLED = false; 
const int intervalBlikani = 100; 

void setup() {
  mojeServo.attach(servoPin);
  pinMode(ledZelenaPin, OUTPUT);
  pinMode(ledOranzovaPin, OUTPUT);
  pinMode(ledCervenaPin, OUTPUT);
}

void loop() {
  unsigned long aktualniCas = millis();
  
  int hodnotaPotenciometru = analogRead(potenciometrPin);
  int uhelServa = map(hodnotaPotenciometru, 0, 1023, 0, 180);
  mojeServo.write(uhelServa);

  // --- LOGIKA ALARMU (Zkráceno) ---
  if (uhelServa <= 60) {
    digitalWrite(ledZelenaPin, HIGH);   
    casVstupuDoCervene = 0; 
  } else if (uhelServa > 120) {
    // ČERVENÁ ZÓNA
    if (casVstupuDoCervene == 0) casVstupuDoCervene = aktualniCas;

    if (aktualniCas - casVstupuDoCervene < limitAlarmu) {
      digitalWrite(ledCervenaPin, HIGH); 
    } else {
      // ALARM - BLIKÁNÍ
      if (aktualniCas - casPoslednihoBliknuti >= intervalBlikani) {
        casPoslednihoBliknuti = aktualniCas;
        stavBlikaniLED = !stavBlikaniLED;
        digitalWrite(ledCervenaPin, stavBlikaniLED ? HIGH : LOW);
      }
    }
  }
}
</code></pre>
</div>
