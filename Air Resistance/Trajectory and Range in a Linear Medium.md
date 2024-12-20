# Trajectory and Range in a Linear Medium

From our prior studies linear air resistance, we can now describe a projectile's motion with linear air resistance. Taking the normal notation for direction (and thus making $v_{\text{ter}}$ reverse signs), our equations become 

```math
\begin{array}
 \\
x(t) = v_{x_{0}} \tau (1- e^{-t/\tau}) \\
y(t) = (v_{y_{0}} + v_{\text{ter}})\tau(1-e^{-t/\tau})- v_{\text{ter}}t
\end{array}
```

Now, we can just look at these and be quiet happy, for every $t$ we can find an object's position relative to it's initial position (note how we let $x_{0}$ and $y_{0}$ both be zero), however let us see if we can better describe it's trajectory. We can go ahead and solve the first equation for $t$ and put that into our second equation where with a bit of work we end up deriving 

$$
y = \frac{{v_{y_{0}} + v_{\text{ter}}}}{v_{x_{0}}} x + v_{ter}\tau \ln\left( 1-\frac{x}{v_{x_{0}}\tau} \right)
$$

This equation here now relates our $x$ position to our $y$ position, and while yes it makes absolutely no sense as it stands, we can see an interesting result. See as $x \to v_{x_{0}}\tau$, we start to reach an asymptote for our function there, as interesting result showing that we cannot throw an object infinitely far if there was no "floor" for the object, unlike our work in a vacuum. 

## Horizontal Range

Now, let us begin to describe the object's range, after all this is a rather important piece of information when working with projectiles. Recall that our range in a vacuum can be described as

$$
R_{\text{vac}} =  \frac{{2v_{x_{0}}v_{y_{0}}}}{g}
$$

Turning our attention towards our air resistance case, we want to look for where $y = 0$, for some value of $x$, our value of $x$ is going to be our range $R$, thus we are looking for the solution of

$$
0 = \frac{{v_{y_{0}} + v_{x_{0}}}}{v_{x_{0}}}R + v_{\text{ter}}\tau \ln\left( 1-\frac{R}{v_{x_{0}}\tau} \right)
$$

well this is rather simple, we can't. Primarily because this is a *transcendental equation*, meaning like $e$ or $\pi$, we cannot fully pinpoint all of its information. Thus, we are stuck with numerical solutions, but this itself poses a problem, this does not fully discuss any of the relationships we see in our physical properties. Certainly we get a value, but we do not get *why*, and that itself is an issue. Hence, we shall endeavor to find an *approximate solution*, to better understand what in the hell is going on. 

Let us just analyze our equation, first thing first we really only have one variable $R$, that's good, each of our other values will be fixed and thus we are looking only at terms that vary with $R$. We know, just from our experience the effects of air resistance must be rather small, thus, we are looking for where changes in our values are going to be the most pronounced. Our first term is fine and dandy, it's just a simple multiplier, I would not worry about that, any changes there is going to be expanded by some fixed amount. But the second term, we can see that if $v_{ter}$ is large and $\tau$ are large as well that natural log is going to be getting closer and closer to zero, making that whole left term disappear. Thus, we should focus on that, as that natural log can create large changes in our values. We can use a Taylor Series expansion to make our function pretty close to our actual value. The Taylor Series expansion for $\ln(1-\epsilon )$ is 

$$
\ln(1-\epsilon) = -\left( \epsilon + \frac{1}{2}\epsilon^{2} + \frac{1}{3} \epsilon^{3}+\dots \right)
$$

which for our uses we can get a pretty good approximation with just the first three terms, fixing up our original equation we have

$$
\left[ \frac{{v_{y_{0}} + v_{\text{ter}}}}{v_{x_{0}}} \right]R - v_{ter}\tau \left[ \frac{R}{v_{x_{0}}\tau}  + \frac{1}{2} \left( \frac{R}{v_{x_{0}}\tau} \right) ^{2} + \frac{1}{3 }\left( \frac{R}{v_{x_{0}}\tau} \right) ^{3} \right] = 0
$$

With a bit of slight reorganization, we derive 

$$
R = \frac{{2v_{x_{0}}v_{y_{0}}}}{g} - \frac{2}{3v_{x_{0}}\tau}R^{2}
$$ 

which for a large enough $\tau$ we get 

$$
R \approx R_{\text{vac}}
$$

treating this like an iterative process we get

$$
R \approx R_{\text{vac}}\left( 1-\frac{4v_{y_{0}}}{3v_{\text{ter}}} \right)
.$$

An interesting result, because as we can see the real things affecting our new range with air resistance is our terminal velocity and our initial $y$-velocity.  Keeping this in mind, this makes sense for an object with an infinite terminal velocity we can see our range begins to approach our range in a vacuum. The lower the terminal velocity the lower our range will be. This goes up until $v_{\text{ter}} = v_{y_{0}}$, where if our max velocity is our initial throwing velocity then the projectile's only "option" is to fall. This also matches our intuition that the effects of air resistance oughta be really small. 
