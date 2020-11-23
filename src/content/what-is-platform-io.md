#### Well its an IDE... A better one?

The traditional Arduino IDE is complicated. Behind that snazzy text editor we all know and love, there is a lot going on. To make matters worse, not much of this is exposed in a friendly fashion. Although the project is open source, its not simple to follow and customize.

Enter Platform.io, the "modular" alternative. This new IDE on the block promises to add flexibility, do not conform you to anything. It allows you to use more than the Arduino platform.

Whats also nice about it, is that you can use it as a standalone, or as plugins for popular open source IDE's like Visual Studio Code or Atom.

Platform.io is great when you can get it working, it is quite extensible in our experience. However it does have quite a learning curve when setting up. When you do get the hang of it, there are advanced scripting features that could allow you to do unit testing, construct CI pipelines and much more...

A question you might be asking now is, are my .ino files compatible? Well the short answer is no. Heres a quick blink example to explain why...

```cpp
/* Arduino Example Blink.ino */

void setup()
{
  // initialize LED digital pin as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop()
{
  // turn the LED on (HIGH is the voltage level)
  digitalWrite(LED_BUILTIN, HIGH);
  // wait for a second
  delay(1000);
  // turn the LED off by making the voltage LOW
  digitalWrite(LED_BUILTIN, LOW);
   // wait for a second
  delay(1000);
}
```
Above you can see the arduino code, with a small addition of the Arduino.h header file (plus some definitions), you can convert this script into something you can run in platform.io, there may be other differences but that is out of the scope of this blog.

```cpp
/* Platform.io Example Blink.cpp */

#include "Arduino.h"

// Set LED_BUILTIN if it is not defined by Arduino framework
// #define LED_BUILTIN 13

void setup()
{
  // initialize LED digital pin as an output.
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop()
{
  // turn the LED on (HIGH is the voltage level)
  digitalWrite(LED_BUILTIN, HIGH);
  // wait for a second
  delay(1000);
  // turn the LED off by making the voltage LOW
  digitalWrite(LED_BUILTIN, LOW);
   // wait for a second
  delay(1000);
}
```
Platform.io is reasonable young for an open source project, we are yet to see what future it has. However it currently is a good alternative for an IDE for those who want to move out of the Arduino space, into more native c and cpp like code.

end;
