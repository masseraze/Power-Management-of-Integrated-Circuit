# Project

Voltage mode of buck converter with 0.18 &mu;m CMOS Process\
<strong>Specification:</strong>\
Convert voltage from 1.8V to 1V\
off-chip Inductor: 4.7 &mu;m with 100m&Omega;\
off-chip Capacitor: 3.3 &mu;m with 30m&Omega;\
V<sub>ref</sub> = 0.6V

## Schematic
we will design error amplifier as voltage-mode compensator
<div align=center><img width = "50%" src="https://user-images.githubusercontent.com/26044795/208688439-f39ddc59-15df-471d-ab07-2a2c385df33c.png"/></div>

## Simulate whole system with simulink
Caculate the RC value for voltage-mode compensator
<div align=center><img width = "50%" src="https://user-images.githubusercontent.com/26044795/208710842-b5b3c830-b7c4-4f23-b84d-b1e7f61afc11.png"/></div>

## design compensator with hspice
#### valid the RC value simulated by sisotool with ideal amplifier
Pole one(P<sub>1</sub>): 308kHz, Pole two(P<sub>2</sub>): 1.6MHz\
Zero one(Z<sub>1</sub>): 6.72kHz, Zero two(Z<sub>2</sub>): 15.5kHz
<div align=center><img width = "50%" src="https://user-images.githubusercontent.com/26044795/211188190-0dbfe951-5a45-4d5a-aa0e-40490e372fa6.png"/></div>

#### Implement two-stage amplifier for amplifier
Although the dc gain does not meet our expectations, the compensator's other functions work.
<div align=center><img width = "40%" src="https://user-images.githubusercontent.com/26044795/211188706-e23b0a97-dd72-4b04-b4b4-c48629c2a256.png"/></div>


## Outcome

#### 500mA (heavy load)
Output voltage: 999.6mV, Output voltage ripple: 0.74mV, efficiency &eta;:74.4%
<div align=center><img width = "50%" src="https://user-images.githubusercontent.com/26044795/208713514-0414e466-8bb6-4540-a4a3-8df85844dc5e.png"/></div>

#### 10mA (light load)
Output voltage: 999.74mV, Output voltage ripple: 0.8mV, efficiency &eta;:80.8%
<div align=center><img width = "50%" src="https://user-images.githubusercontent.com/26044795/208711556-cb6dfcf0-37d4-461c-b0bb-0ab9dc3a3f12.png"/></div>

#### transient response plot (from low to heavy load)
transient time: 13&mu;s
<div align=center><img width = "50%" src="https://user-images.githubusercontent.com/26044795/211187647-ff84e052-c70a-4b46-a9e0-e7eaf89ccff3.png"/></div>

#### transient repsonse plot (from heavy to low load)
transient time: 10&mu;s
<div align=center><img width = "50%" src="https://user-images.githubusercontent.com/26044795/211187652-607fba22-3005-4741-a495-1f919fee57c8.png"/></div>
