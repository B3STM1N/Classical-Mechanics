It is time, we have dealt with linear air resistance for a while now, and we've even developed some pretty good equations to describe an object's range and trajectory. However, working in mechanics we are not just concerned with extremely small or slow objects, we are oftentimes interested in the movement of large objects that are subject to much more air resistance. Before, we described linear air resistance to be\
$\vec{f}=-b\vec{v}$\
but now it is\
$\vec{f}=-cv^{2}\hat{v}$\
where $\hat{v}$ is our unit vector for the velocity $v$. Like before for a projectile there are only really two forces, hence by Newton's second law we have 
$$m\dot{v}=m\vec{g}-\vec{f}$$ 
and just like before, we are going to separate this into two equations and solve for both. But to briefly point this out, this is a *nonlinear differential equation* and unlike our nice linear drag, this is going to be a bit rougher. Inevitably, we will find that we can only solve these equations numerically and not analytically, this is another blow to our egos. However, first thing first, vertical and horizontal quadratic drag.

# Horizontal Drag with Quadratic Drag

Like what we did for linear air resistance, we shall begin by having an object move horizontally and being subject to quadratic drag. For a visual representation, think of a cyclist coasting to a stop of a flat road, neglecting all other forces beyond just the air resistance. Thus, we can describe our forces as 
$$m\dot{v}_{x} = -cv^{2}$$
or $m \frac{dv}{dt} = -cv^{2}$. We will solve this via the separation of variables technique, where if you are a mathematician, avert your eyes. 
$$
\begin{array}
 \\
\frac{dv}{v^{2}} = -cm\;dt \\
\implies \int_{v_{0}}^{v} \frac{1}{v^{2}}\; dv = -cm\int_{t_{0}}^{t} 1\; dt \\
\implies m\left( \frac{1}{v_{0}} - \frac{1}{v} \right) = -ct \\
\implies v(t) = \frac{v_{0}}{1 + \frac{cv_{0}t}{m}} = \frac{v_{0}}{1+\frac{t}{\tau}} 
\end{array}
$$
where $\tau = \frac{m}{cv_{0}}$. Do note that this is different than our previous definition for $\tau$. Now with a quick integration and a bit of luck we can derive $$
x(t) = v_{0}\tau \ln \left( 1 + \frac{t}{\tau} \right) 
$$(note how our initial $x$-position is $0$). Awesome! This was not too hold to solve, but there are a few things we must note that there are some differences with our linear drag, and analysis of this equation may lead to some new insights. We see that our velocity does not decrease exponentially, rather it moves closer to a fraction. We can also see that we cannot stop, or rather, that it seems that as $t \to \infty$, while our velocity decreases we do not find $v \to 0$, this seems strange. However, we are forgetting the humble linear air resistance, which shall begin to dominate in this strange scenario, and with that we are able to reach $0$, fixing this issue of our derivation. 

# Vertical Motion with Quadratic Drag

Y'know the deal, throw that particle vertically to the ground. Thus, we can say that our forces again are $$
m \dot{v}_{y} = mg - cv^{2}. 
$$ now before we do anything crazy, let us remember that finding our terminal velocity is huge, and in fact we can find that $$
v_{\text{ter}} = \sqrt{ \frac{mg}{c} } 
$$ which is slightly different than what we had before. We can, however, incorporate this into our prior equation, netting us $$
\dot{v}_{y} = g\left( 1- \frac{v^{2}}{v_{\text{ter}}^{2}} \right) 
$$ With a quick separation of variables and the common knowledge we totally have about hyperbolic functions we can derive $$
\frac{v_{\text{ter}}}{g}\tanh ^{-1}\left( \frac{v}{v_{\text{ter}}} \right)  = t$$
which with a bit more work nets us $$
v = v_{\text{ter}} \tanh \left( \frac{gt}{v_{\text{ter}}} \right) 
$$
With a bit of integration again, we can find our position which happens to be $$
y = \frac{(v_{\text{ter}})^{2}}{g} \ln \left[ \cosh \left( \frac{gt}{v_{\text{ter}}} \right)  \right] . 
$$
Nice! Like before we know have equations that fully define our motion, but do note that we had to use hyperbolic functions. These are going to be much more common moving forward so **learn them**. Beyond that, these equations let us devolve any vertical problem into a plug and chug situation.

# Quadratic Drag with Horizontal and Vertical Motion

This is hell. A projectile subject to quadratic drag, has two force components $$
\begin{array}
 \\
m \dot{v}_{x} = -c \sqrt{ v_{x}^{2} + v_{y}^{2} }v_{x}\\ 
m \dot{v}_{y} = -mg - c \sqrt{ v_{x}^{2} + v_{y}^{2} }v_{y}
\end{array}
$$ These two equations may not seem like much, but notice how they are **not uncoupled**, that means to solve one we must find variables that satisfy both equations... We also cannot just use the equations we just made for this problem due to the picky nature of our movement. We may recall our definition of drag $\vec{f} = -cv^{2}\hat{v}$, note that we can rewrite this as $\vec{f} = -cv \vec{v}$, well this poses an issue as for a specific direction we will have to solve using our components to separate out our *total velocity*. This leads us to the fact that we may only truly solve this problem numerically. It is a great shame, however, it is better than nothing. So when working out problems with quadratic drag, make sure you have your favorite computer program with you to hash this problem out. 
