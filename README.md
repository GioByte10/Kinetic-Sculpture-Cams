# Kinetic-Sculpture-Cams

<div align="center">
  <img src="assets/sculpture_.png" alt="description of gif" width="900"/>
</div>

<br><br>

<img src="assets/cams_front_.png" align = "right" alt="front of cams" width="250"/>

This kinetic sculpture is designed to simulate an ocean wave with small height relative to its wavelength, which approximates a sine function. In order to achieve this behaviour, I have created $$n$$ _eccentric_ cams which are identical to each other, but have a phase shift relative to each other, such that each subsequent cam is offsetted by $$Φ$$ degrees. Each cam has its own rectangular follower that falls and rises as the cam moves.

Making the (theoretical but not real) assumption that the tangent point of contact between the cam and the rectangular follower is at some point $$y_{T}$$ along $$x=0$$, $$(0, y_{T})$$, I aim to prove that this configuration produces a pure sine function.<br><br>

## References
[Desmos graph](https://www.desmos.com/calculator/odotgpws6i)
<br><br>

## Setup
<img align="left" src="assets/setup.png" alt="setup.png" width="250"/>

Let us start by parametrically defining the equation of a circle $$\vec{r}\(t)$$ with an offset from the origin. Let $$R$$ be the radius, $$a$$ be the x-offset and $$b$$ be the y-offset. So we can define our circle by

$$\vec{r}\(t)=
\begin{bmatrix}
   R\cos\left(t\right)+a\\
   R\sin\left(t\right)+b
\end{bmatrix}
$$

$$t \in [0, 2\pi]$$

<br><br>

In order to represent the circle as it rotates for an angle $$\theta$$, we will multiply the parametric vector equation by the rotation matrix

$$R\(\theta)=
\begin{bmatrix}
   \cos\left(\theta\right) & -\sin\left(\theta\right)\\
   \sin\left(\theta\right) & \cos\left(\theta\right)
\end{bmatrix}
$$

Such that now we have 

$$\vec{r}\(t, \theta)=R(\theta)
\begin{bmatrix}
   R\cos\left(t\right)+a\\
   R\sin\left(t\right)+b
\end{bmatrix}
$$

$$\vec{r}\(t, \theta)=
\begin{bmatrix}
   \cos\left(\theta\right) & -\sin\left(\theta\right)\\
   \sin\left(\theta\right) & \cos\left(\theta\right)
\end{bmatrix}
\begin{bmatrix}
   R\cos\left(t\right)+a\\
   R\sin\left(t\right)+b
\end{bmatrix}
$$

$$\vec{r}\(t, \theta)=
\begin{bmatrix}
   \left(R\cos\left(t\right)+a\right)\cos\left(\theta\right) -\left(R\sin\left(t\right)+b\right)\sin\left(\theta\right)\\
   \left(R\cos\left(t\right)+a\right)\sin\left(\theta\right) +\left(R\sin\left(t\right)+b\right)\cos\left(\theta\right)
\end{bmatrix}
$$

$$\vec{r}\(t, \theta)=
\begin{bmatrix}
   x(t, \theta)\\
   y(t, \theta)
\end{bmatrix}
$$

## Derivation
We know that, at its highest point, the tangent to the circle will have a vector $$\vec{v}(t, \theta)$$, with a negative x-component and a zero y-component

<div align="center">
  <img src="assets/tangent.png" alt="description of gif" width="300"/>
</div>

<br>

We can find $$\vec{v}(t, \theta)$$ by

$$\vec{v}(t, \theta)=\frac{d}{dt}\vec{r}\(t, \theta)$$

$$\vec{v}(t, \theta)=\frac{d}{dt}\begin{bmatrix}
   \left(R\cos\left(t\right)+a\right)\cos\left(\theta\right) -\left(R\sin\left(t\right)+b\right)\sin\left(\theta\right)\\
   \left(R\cos\left(t\right)+a\right)\sin\left(\theta\right) +\left(R\sin\left(t\right)+b\right)\cos\left(\theta\right)
\end{bmatrix}$$

$$\vec{v}(t, \theta)=\begin{bmatrix}
   -R\sin\left(t\right)\cos\left(\theta\right)-R\cos\left(t\right)\sin\left(\theta\right)\\
   -R\sin\left(t\right)\sin\left(\theta\right)+R\cos\left(t\right)\cos\left(\theta\right)
\end{bmatrix}$$

$$\vec{v}(t, \theta)=\begin{bmatrix}
   v_{x}(t, \theta)\\
   v_{y}(t, \theta)
\end{bmatrix}$$

Let us solve for the y-component, $$v_{y}$$, when it is equal to $$0$$

$$v_{y}(t, \theta)=0$$

$$-R\sin\left(t\right)\sin\left(\theta\right)+R\cos\left(t\right)\cos\left(\theta\right)=0$$

$$R\cos\left(t\right)\cos\left(\theta\right)=R\sin\left(t\right)\sin\left(\theta\right)$$

$$\cos\left(t\right)\cos\left(\theta\right)=\sin\left(t\right)\sin\left(\theta\right)$$

$$\frac{\cos\left(t\right)}{\sin\left(t\right)}\cos\left(\theta\right)=\sin\left(\theta\right)$$

$$\frac{\cos\left(t\right)}{\sin\left(t\right)}=\frac{\sin\left(\theta\right)}{\cos\left(\theta\right)}$$

$$\tan\left(t\right)=\cot\left(\theta\right)$$

Solve for t

$$t=\tan^{-1}\left(\cot\left(\theta\right)\right)$$

Note that

$$\cot\left(x\right)=\tan\left(\frac{\pi}{2}-x\right)$$

Thus

$$t=\tan^{-1}\left(\tan\left(\frac{\pi}{2}-\theta\right)\right)$$

$$t=\frac{\pi}{2}-\theta$$

This means that the highest point on an eccentric cam rotated by $$\theta$$ about the origin is when $$t=\frac{\pi}{2}-\theta$$, at

$$y_{T}=y(t, \theta)=y(\frac{\pi}{2}-\theta, \theta)$$

Note that

$$y(t, \theta)=\left(R\cos\left(t\right)+a\right)\sin\left(\theta\right) +\left(R\sin\left(t\right)+b\right)\cos\left(\theta\right)$$

Then

$$y(\frac{\pi}{2}-\theta, \theta)=\left(R\cos\left(\frac{\pi}{2}-\theta\right)+a\right)\sin\left(\theta\right) +\left(R\sin\left(\frac{\pi}{2}-\theta\right)+b\right)\cos\left(\theta\right)$$

Using identities

$$\cos\left(\frac{\pi}{2}-x\right)=\sin\left(x\right)$$

$$\sin\left(\frac{\pi}{2}-x\right)=\cos\left(x\right)$$

We have

$$y(\frac{\pi}{2}-\theta, \theta)=\left(R\sin\left(\theta\right)+a\right)\sin\left(\theta\right) +\left(R\cos\left(\theta\right)+b\right)\cos\left(\theta\right)$$

$$y(\frac{\pi}{2}-\theta, \theta)=R\sin^{2}\left(\theta\right)+a\sin\left(\theta\right)+R\cos^{2}\left(\theta\right)+b\cos\left(\theta\right)$$

$$y(\frac{\pi}{2}-\theta, \theta)=R\sin^{2}\left(\theta\right)+R\cos^{2}\left(\theta\right)+a\sin\left(\theta\right)+b\cos\left(\theta\right)$$

$$y(\frac{\pi}{2}-\theta, \theta)=R\left(\sin^{2}\left(\theta\right)+\cos^{2}\left(\theta\right)\right)+a\sin\left(\theta\right)+b\cos\left(\theta\right)$$

$$y(\frac{\pi}{2}-\theta, \theta)=R\left(1\right)+a\sin\left(\theta\right)+b\cos\left(\theta\right)$$

$$y(\frac{\pi}{2}-\theta, \theta)=R+a\sin\left(\theta\right)+b\cos\left(\theta\right)$$

Using the sinusoidal indentity

$$a\sin\left(x\right)+b\cos\left(x\right)=\sqrt{a^{2}+b^{2}}\sin\left(x+\tan^{-1}\left(\frac{b}{a}\right)\right)$$

Let

$$A=\sqrt{a^{2}+b^{2}}$$

$$\phi=\tan^{-1}\left(\frac{b}{a}\right)$$

Such that

$$a\sin\left(x\right)+b\cos\left(x\right)=A\sin\left(x+\phi\right)$$

We end up with the sine function

$$y_{T}=y(\frac{\pi}{2}-\theta, \theta)=R+A\sin\left(x+\phi\right)$$

<div align="center">
  <img src="assets/demos.gif" alt="description of gif" width="700"/>
</div>

