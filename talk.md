% CAN We or CAN't We
% Robert <robert@rtward.com> & Joe <kamikazejoe@gmail.com>
%![](static/qrcode.png)<br/>Talk: [${TALK_URL}](${TALK_URL})<br/>Repo: [${REPO_URL}](${REPO_URL})

# Rehash protocol info

 - Mostly used for cars
 - Similar to RS-422 / 485

## High-Speed Bus

![](static/canbus-high-speed.png)

::: notes

 - Each end has 120ohm resistor

:::

## Signaling

 - Signal 1 by driving high and low
 - Signal 0 by allowing them to equalize

## Low-Speed Bus

![](static/canbus-low-speed.png)

::: notes

 - Total resistence should be 100ohm
 - More fault tolerant

:::

## Signaling

 - Signal 1 by driving high and low
 - Signal 0 by inverting 1

## Protocol

 - Wait after message
 - Message start by driving high
 - Start with message ID

## Packet Format

![](static/canbus-frame.png)

## Priority

![](static/canbus-priority.png)

# The Plan!

::: notes

:::

## Step 1: Go to Junk Yard

::: notes

Step 1:
- We need car parts to car hack
- We aren't made of money, so new parts weren't an option
- To the Junk Yard!
- Figure it'll take about an hour, tops.

:::

## Step 2: Purchase Car Parts

- Steering Wheel with Buttons
- Instrument Panel

::: notes

- We weren't looking to do anything too elaborate
- Just want to see some data going across the CAN
- Prove we can read and write data
- Steering Wheel would give us some input to observe
- Instrument panel to write data out to

:::

## Step 3: Wire up, sniff CAN

::: notes

- We take everything home.
- Build a bench unit to test with
- Start sniffing CAN signals

:::

## Success!

![](static/anakin-padme-meme.jpg)

::: notes

:::

# Here's what actually happened...

::: notes

:::

## Step 1: Go to Junk Yard

![](static/junkyard-location.png)

::: notes

- Went as planned.
- Decided on PYP in Washington Park
- Bob and I got there nice an early on the weekend.

:::

## Step 2: No Kids Allowed

![](static/junkyard-hours.png)

::: notes

- Bob brought his son with him.
- Turns out minors aren't allowed in the junk yard.
- Which we probably would've known if we had done the tiniest bit of research

:::

## Step 3: Come Back Another Day

::: notes

- So we came back another day.
- This time we left the children at home.


:::

## Step 4: Go back and get tools

::: notes

- Unfortunately we also left our tools at home.

:::

## Step 5: Return to Junk Yard

::: notes

- So, after driving home, grabbing tools, and driving back we are ready to start 
- after only losing an hour of the estimated hour job.

:::


## Step 6: Selected a random Chevy Riverside because it looked “newish”

![](static/chevy-riverside.png)

::: notes

- So, after driving home, grabbing tools, and driving back we are ready to start 
- after only losing an hour of the estimated hour job.

:::

## Step 7: Attempt to remove steering wheel

![](static/monkey-tools.jpg)

::: notes

- And thus began our shortlived career as mechanics.
- We were immediately stumped by the lack of screws or bolts

:::

## Step 8: Watched Youtube video

![](static/monkey-watching-tv.jpg)

::: notes

- So, we turned to the internet
- Found a instructional video for removing this particular steering wheel

:::

## Step 9: Removed Steering Wheel

![](static/ape-cheer.jpg)

::: notes

- And it still took us way too long to remove it, but we did.
- In this case, there were little release buttons you had to push with a long screwdriver or allen wrench

:::

## Step 10: Oops… Too many wires.

![](static/too-many-wires.png)

::: notes

- So after we finally removed the steering with...
- We expected 2-4 wires.  Instead there was probabably closer to twenty.
- That's way too many wires for CAN bus.

:::

## Step K: Confusion

![](static/confused-monkey.jpg)

::: notes

- Okay. So what do these go to?
- Is there another controller that translates these into CAN?
- We assumed every thing just spoke to the Car's single computer over can.
- We are very confused at this point.  Again due to overconfidence and minimal research

:::

## Step L-12: More Googling

![](static/monkey-computer.jpg)

::: notes

- So more googling, and we start looking for other controllers and the ECU

:::

## Step Delta: Attempting to find ECU

![](static/wheres-waldo.jpg)

::: notes

- We try to follow the various wireing harnesses around, but no luck
- The only think we found was a controller than handled the 4x4 system
- And being a junkyard, we couldn't even be sure it was there

:::

## Step "Fix TypeError: List Not Integer": Failure

![](static/loser.png)

::: notes

- So we accepted our ignorance and decided to head back and do more research and do more planning
- Next time we'll decide on a specific vehicle.
- Check the website and make sure they have it at the junkyard
- Learn how to remove the parts beforehand. 

:::

# Things talking on the network

## ECU (Electronic Control Unit)

::: notes

The generic term for all the "computers" in the car.

The specific terms and what computers do is dependent on the manufacturer, but there's some generic ones.

:::

## ECM (Engine Control Module)

![alt text](static/ecm.png)

::: notes

The computer that controls the engine.

:::

## TCM (Transmission Control Unit)

::: notes

The computer that controls the transmission / shifting.

:::

## BCM (Body Control Module)

![alt text](static/bcm.png)

::: notes

The computer used to control locking, hvac, and other internal controls.

:::

## Radio / In Car Entertainment

::: notes

The computer used to control locking, hvac, and other internal controls.

:::

# Local Interconnect Network (LIN)

Great, another thing.

## LIN

 - One wire serial format
 - Less reliable then CAN
 - But, cheaper
 - Max 16 nodes, one master with 15 slaves
 - Consistent latency

::: notes

Usually used on a gateway to the CANBUS

:::

## How to actually play with it
## Tools
## MCP2515

# Inputs
## Steering Wheel Controls

::: notes

Sometimes directly connected to the BCM

Sometimes connected to a LINBUS

:::

# Outputs
## Instrument Cluster

# Simulator

::: notes

:::

# Live car connection

::: notes

:::

# Game Plan
## Go to Defcon and talk to the car hacking village
## Pick a car with a BCM
## Research how to take it apart
## Pull out the
## BCM
## Steering Wheel
## Instrument Cluster
## Wiring Harness
## Hook up to CAN port on BCM-ECU and power up
## Snoop on CANBUS
## Write to Displays

# Stretch Goals
## Game interface
## Remote testing

--- 

Robert <robert@rtward.com> & Joe <kamikazejoe@gmail.com>

![](static/qrcode.png)

Talk: [${TALK_URL}](${TALK_URL})

Repo: [${REPO_URL}](${REPO_URL})
