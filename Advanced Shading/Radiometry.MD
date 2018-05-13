# Radiometry

Radiometry的中文意思叫做辐射学，为什么图形学中的shading部分必须要以辐射学为基础呢？我想是因为Shading是模拟真实物理世界中光与物体交互的过程，在这个过程中，必将会有能量的转移，所以要用辐射来描述光与物体的交互过程中能量的变化。

## Radiometry中几个重要的概念

-  Radiant energy(辐射能量),用Q表示，单位是焦耳(J)。每一个光子都有一定的radiant energy,频率越高能量就越高。


-  Radiant flux(辐射通量）,用Φ表示，单位是瓦特(watt)。它的定义是： radiant flux is the radiant energy emitted, reflected, transmitted or received per unit time. 也就是说在单位时间内发出、反射、转移或者接受的辐射能量,它可以用来表示光源的功率。dΦ = dQ/dt。

-  Irradiance(辐射照度),用E表示，单位是 W/m^2。它的定义是： irradiance is the radiant flux received by a surface per unit area.也就是说一个表面在单位面积上接收到的辐射通量。E=dΦ/dA.Irradiance 用来描述光源对表面照射时，单位面积上的辐射通量。

-  Radiant exitance，用M表示。radiant exitance表示从被照射表面逃离的irradiance。


在计算irradiance时，通常要用垂直于光线入射方向的平面来计算，当然也可以将光线分解在平面法线方向来进行计算。
当场景里的光源是比较远的光源的时候，比如太阳光，可以认为irradiance恒定，即与光源到被照射表面的距离无关。当光源比较近的时候或者场景比较大的时候，irradiance不能被视为恒定值，其值与光源到被照射表面距离的平方成反比。

但是怎么样确定这个光源多远算是远，多近才算是近呢？Lambert提出了一个5倍原则：如果光源到被照射表面的距离比光源的宽度的五倍还要大，那么我们就认为irradiance随着距离增加而衰减。

- Solid angle(立体角),用Ω表示，单位是sr(steradians)。

立体角的定义是这样的，将空间中一个曲面投影到半径为1的单位球上，这个投影的面积就是立体角的值。

在球坐标下，我们取空间中该曲面的一个微小的面积dA，那么我们把这个面积当做矩形来处理，它的两边长分别可以用曲边扇形弧长公式求得，分别为rdθ和rsinθdφ,那么就有dA = rdθ*rsinθdφ。显然在单位球上r=1，那么在单位球上的微小面积dA'=sinθdθdφ。

立体角的性质之一就是立体角元在半球球面上的积分为4π,也就是说Ω = A' = ∫dA' = ∫∫sinθdθdφ = 4π

- Radiance(辐射亮度),用L表示，单位是W/(sr*m^2)，它的定义是：radiance is the radiant flux emitted,reflected, transmitted or received by a given surface, per unit solid angle per unit projected area.它与irradiance的不同在于,radiance是在每个单位立体角上进行测量的。







