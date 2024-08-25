# HeadPhone-Amplifier


## Highpass filter

### Calculating values

Given that the filter is supposed to filter out unwanted frequencies, in this case frequencies between 20-20khZ which are out of the audible range. Since this is a highpass filter it is the lower end of the spectrum which we are focusing on. Good practice is to use about a 10th of the minimum frequency. In this case $f_{C}=\frac{20Hz}{10}=2Hz$, the resistor is already predetermined only the capacitor needs to be calculated.

$f_{c}=2Hz$
$R=47k\Omega$
$C=\frac{1}{2\pi Rf_{c}}\approx1.69\mu F$

In this project we are going to be using componments of the E12 series, therefor C needs to be changed to a fitting value $(C=1.8\mu F)$. Lets see if $f_{C}$ is still a reasonable value.

$f_{C}=\frac{1}{2\pi RC}\approx1.88Hz$

$f_{c}$ is till a good value. Now all the values have been set for the filter

$R=47k\Omega$
$C=1.8\mu F$
$f_{C}=1.88Hz$

### Getting $V_{out}$

$\omega =2\pi f$
$X_{c}=\frac{1}{\omega C}$
<br>
$$V_{out}=V_{in}*\frac{R}{\sqrt{ X_{c}^2+R^2 }}$$

### Transfer function

$Z_{c}=\frac{1}{j\omega C}$
<br>
$$V_{out}=V_{in}*\frac{R}{R+\frac{1}{J\omega C}}$$
**Simplifying**
$$
V_{out}=V_{in}*\frac{R}{R\left( 1+\frac{1}{j\omega C} \right)}=V_{in}*\frac{R}{1+\frac{1}{j\omega C}}=V_{in}*\frac{j\omega RC}{1+j\omega RC}
$$
**Transfer function**
$$
H(j\omega)=\frac{V_{out}}{V_{in}}=\frac{j\omega RC}{1+j\omega RC}\implies H(j\omega)=\frac{j\omega RC}{1+j\omega RC}
$$
$\tau=RC$
**Final function**
$$
H(j\omega)=\frac{j\omega \tau}{1+j\omega \tau}
$$
