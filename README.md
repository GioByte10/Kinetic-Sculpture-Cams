# Kinetic-Sculpture-Cams

<div align="center">
  <img src="assets/sculpture_.png" alt="description of gif" width="900"/>
</div>

<br><br>

<img src="assets/cams_front_.png" align = "right" alt="front of cams" width="150"/>

This kinetic sculpture is designed to simulate an ocean wave with small height relative to its wavelength, which approximates a sine function. In order to achieve this behaviour, I have created $$n$$ _concentric_ cams which are identical to each other, but have a phase shift relative to each other, such that each subsequent cam is offsetted by $$Φ$$ degrees. Each cam has its own rectangular follower that falls and rises as the cam moves.

Making the (theoretical but not real) assumption that the tangent point of contact between the cam and the rectangular follower is at some point $$y_{t}$$ along $$x=0$$, $$(0, y_{t})$$, I aim to prove that this configuration produces a pure sine function.

## Setup
Let us start by parametrically defining the equation of a circle with an offset from the origin. Let $$R$$ be the radius, $$a$$ be the x-offset and $$b$$ be the y-offset. So we can define our circle by

$$\left(R\cos\left(t\right)+a,\ R\sin\left(t\right)+b\right)$$
$$t \in [0, 6\pi]$$

<div align="center">
  <img src="setup.png" alt="setup.png" width="900"/>
</div>
