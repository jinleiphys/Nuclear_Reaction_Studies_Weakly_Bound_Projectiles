---
# You can also start simply with 'default'
theme: hep
preTitle: "Nuclear Reaction Studies Using Weakly Bound Projectiles: Structure and Dynamics"
authors:  # First author should be the presenter
  - Jin Lei: ["School of Physics Science and Engineering, Tongji University, Shanghai 200092, China."] 
meeting: "International Workshop on Structures and Reactions of Exotic Nuclei, June 24th-26th, 2025, Shanghai, China"
preDate: "2025-06-25"
---


<!-- <img id="ATLAS" src="/logo/tongji.jpeg"> </img> -->

<style scoped>
#ATLAS {
  width: 180px;
  position: absolute;
  right: 3%;
  bottom: 4%;
  /* background-color: #2B90B6;
  background-image: linear-gradient(45deg, #4EC5D4 15%,rgb(72, 97, 107) 50%); */
}
</style>

---
layout: pageBar
---

# Nuclear Reactions: use light weakly bound projectiles

<div class="grid grid-cols-2 gap-6 h-96">
  <!-- Left half: Large Chart of Nuclides -->
  <div class="text-center">
    <img src="/pics/chart_nucl.png" class="w-full h-full object-contain mb-2">
  </div>
  
  <!-- Right half: Other images stacked -->
  <div class="grid grid-rows-2 gap-4">
    <div v-click>
      <div class="text-center">
        <img src="/pics/incomplete_fusion.png" class="w-full h-40 object-contain mb-1">
        <p class="text-sm">Incomplete fusion of weakly bound projectiles</p>
      </div>
    </div>
    <div v-click>
      <div class="text-center">
        <img src="/pics/Halo_Nucleus.png" class="w-full h-40 object-contain mb-1">
        <p class="text-sm">Properties of halo nuclei</p>
      </div>
    </div>
  </div>
</div>

---
layout: pageBar
---

# What are Nuclear Reactions?

<div class="grid grid-cols-2 gap-6 h-96">
  <div class="text-center">
    <img src="/pics/reaction.png" class="w-full h-full object-contain mb-2">
  </div>
  <div class="grid grid-rows-4 gap-4">
    <div v-click>
      <div class="text-left space-y-1">
        <p class="text-xl" style="color: #EA33F0;">Extract optical potential, rms radius, density distributions</p>
      </div>
    </div>
        <div v-click>
      <div class="text-left space-y-1">
        <p class="text-xl" style="color: #EA33F0;">Extract spin, parity, spectroscopic factors example: <sup>132</sup>Sn(d,p)<sup>133</sup>Sn</p>
      </div>
    </div>
    <div v-click>
      <div class="text-left space-y-1">
        <p class="text-xl" style="color: #EA33F0;">Study nuclear dynamics properties of halo nuclei</p>
      </div>
    </div>
    <div v-click>
      <div class="text-left space-y-1">
        <p class="text-xl" style="color: #4A9CF7;">Provide energy for star burning synthesis of elements</p>
      </div>
    </div>
  </div>
</div>

---
layout: pageBar
---

# Outline

<div class="h-full flex flex-col justify-center">
  <ul class="text-3xl space-y-4">
    <li style="color: grey;">Introduction</li>
    <li>Modeling the Nuclear Reactions in Few-body Models</li>
    <li>Computing the Breakup Cross Sections</li>
    <li>Conclusions</li>
  </ul>
</div>

---
layout: pageBar
---

# Modeling the Elastic Scattering in two-body model 
Take the use of effective interactions

- **Elastic scattering** occurs when two particles interact and separate without any change in their internal energy states or particle identities
<v-click>

- The elastic scattering can be described by a **two-body model** with an effective interaction

- We developed a new computer code, **C**omplex-scaled **O**ptical and cou**LO**mb **S**cattering **S**olver (**COLOSS**), using the complex scaling method to compute elastic scattering cross sections
  
  *J. Liu, **JL**, Z. Ren, Computer Physics Communications* **311** (2025) 109568
</v-click>
<v-click>

- **Schrödinger equation:**
  $$\left[-\frac{\hbar^2}{2 \mu} \frac{\mathrm{d}^2}{\mathrm{d} r^2}+\frac{\hbar^2}{2 \mu} \frac{\ell(\ell+1)}{r^2}+U_N(r)\right] \psi_{\ell}(r)=E \psi_{\ell}(r)$$

- **Wave function separation:**
  $$\psi_{\ell}(r)=e^{i \sigma_{\ell}} F_{\ell}(\eta, k r)+\psi_{\ell}^{\mathrm{sc}}(r)$$
</v-click>
<v-click> 

- **Complex scaling transformation:**
$$\left[E-H^\theta(r)\right] \psi_{\ell}^{\mathrm{sc}, \theta}(r)=e^{i \theta / 2} e^{i \sigma_{\ell}} \tilde{U}_N\left(r e^{i \theta}\right) F_{\ell}\left(\eta, k r e^{i \theta}\right)$$
</v-click>

---
layout: pageBar
---

# Modeling the Elastic Scattering in two-body model 
Take the use of effective interactions
- **Wave function expansion:**
  $$\psi_{\ell}^{\mathrm{sc}, \theta}(r)=\sum_{j=1}^{N_r} c_j g_j(r)$$

- **Linear equation system:**
  $$\sum_{j=1}^{N_r}\left[E \mathbf{N}_{ij}-\mathbf{H}_{ij}^\theta\right] c_j= b_i^\theta$$

- **Results:**
<div class="flex justify-center gap-6 mt-8">
  <v-click>
    <img src="/pics/d93Nb.png" alt="d + 93Nb scattering" class="w-72 h-48 object-contain">
  </v-click>
  
  <v-click>
    <img src="/pics/6Li208Pb.png" alt="6Li + 208Pb scattering" class="w-72 h-48 object-contain">
  </v-click>
  
  <v-click>
    <img src="/pics/n56Fe.png" alt="n + 56Fe scattering" class="w-72 h-48 object-contain">
  </v-click>
</div>

---
layout: pageBar
---

# Emulating the Reaction Observables
Needs for the uncertainty quantification

- Optical potentials: $U_N(r;\boldsymbol{\omega})=V_C(r;R_C)+V_0f(r;R_R,a_R)+iW_0f(r;R_W,a_W)+iW_s\frac{d}{dr}f(r;R_{WS},a_{WS})$

<v-click>

- Parameter set $\boldsymbol{\omega}=(R_C, V_0, W_0, W_s, R_R, a_R, R_W, a_W, R_{WS}, a_{WS})$     <span style="color:#FF2600;"> **10 dimensions!**</span>
</v-click>

<v-click>

- In Bayesian statistics, one use Markov chain Monte Carlo (MCMC) methods to sample from the posterior: 
</v-click>

<v-click>
<div class="flex justify-center mt-6">
  <img src="/pics/emu_simu.png" alt="Description" class="w-180 h-30 object-contain">
</div>
</v-click>

<v-click>
<div class="grid grid-cols-3 gap-5 items-center justify-center">
<div class="col-span-2">
<div class="text-center text-sm mb-2">
Fig. Taken from: Odell et al,. PRC <strong>109</strong>, 044612
</div>
<img src="/pics/emulator_vs_simulator.png" alt="Description" class="w-180 h-60 object-contain">
</div>
<div class="col-span-1">

e.g. 50,000 samples

- Emulator: 50,000*0.001s = 50s

- Simulator: 50,000*0.1s = 5000s

<span style="color:#FF2600;"> **100 times faster!** </span>
</div>
</div>
</v-click>
---
layout: pageBar
---

# Eigenvector Continuation
The emulator method

**Eigenvector continuation** is a method to construct an emulator for the reaction observables.  <span style="color:#FF2600;">Frame et al., PRL 121 032501 (2018)</span>

<v-click>

- Calculate $|\psi(\boldsymbol{\omega_i})\rangle$, $i=1,2,\ldots,N_\mathrm{EC}$ on different training parameter points, $\boldsymbol{\omega_i}$s are radomly sampled from whole parameter space
</v-click>

<v-click>

- Use the set of solutions $\{|\psi(\boldsymbol{\omega}_i)\rangle\}_{i=1}^{N_\mathrm{EC}}$ as the new **non-orthogonal** basis to construct a **subspace** of the solution space for solving the eigenvalue problem or linear equation at the target point.
</v-click>

<v-click>
<div class="grid grid-cols-3 gap-5 items-center justify-center">
<div class="col-span-2">
<div class="text-center text-sm mb-2">
Fig. Taken from: Drischler et al., Front. Phys. <strong>10</strong> 1092931 (2022)
</div>
<img src="/pics/emulator_space.jpeg" alt="Description" class="w-180 h-80 object-contain">
</div>
<div class="col-span-1">

Many extensions of the method have been developed, e.g.:

- **NCSM**: <span style="color:#FF2600;">König et al., Phys. Lett. B <strong>810</strong> 135814 (2020)</span>

- **CC**: <span style="color:#FF2600;">Ekström et al., Phys. Rev. Lett. <strong>123</strong> 252501 (2019)</span>

- **Pairing Hamiltonian**: <span style="color:#FF2600;">Companys et al., Phys. Rev. C <strong>109</strong> 024311 (2024)</span>

- **Resonance**: <span style="color:#FF2600;">Yapa et al., Phys. Rev. C <strong>107</strong> 064316 (2023)</span>

... ...
</div>
</div>
</v-click>

---
layout: pageBar
---

# Building the Emulator Using CSM
Consistent basis for all partial waves

<div class="grid grid-cols-5 gap-5 items-center justify-center">
<div class="col-span-2 text-center">
<div class="mb-2">

$n$+$^{40}$Ca elastic scattering
</div>
<img src="/pics/n40Ca.png" alt="Description" class="w-180 h-80 object-contain">
</div>
<div class="col-span-1">

- Emulated results are accurate

- Reduced basis size is small

- The results are converged rapidly
</div>
<div class="col-span-2 text-center">
<div class="mb-2">

$^{11}$Be+$^{64}$Zn elastic scattering
</div>
<div class="mb-2">

<span style="color:#FF2600;">**Need $\ell_{max}=60$ for convergence**</span>
</div>
<img src="/pics/11Be64Zn.png" alt="Description" class="w-180 h-80 object-contain">
<div class="mt-2 text-sm">
Exp. Data taken from Di Pietro et al. PRL 105, 022701
</div>
</div>
</div>

Define the mean of absolute relative error as: 
$\epsilon = \sum_i \frac{|\sigma_{E,i}-\sigma_{0,i}|}{\sigma_{0,i}}$

More details can be found in: <span style="color:#FF2600;">J. Liu, **JL**, Z. Ren, Phys. Lett. B 858 (2024) 139070</span>

---
layout: pageBar
---

# Modeling the Reaction in three-body model 
More degree of freedom invloved, can be used to study transfer and breakup reactions

- Solving the **three-body** Schrodinger equation：**two-body** projectile with inert cores on inert target (take d+A system as an example)

$$E|\Psi\rangle =H |\Psi\rangle   \ \ \ \ \ \color{#FF2600}{\to}   \ \ \ \ \ \color{#000000}{H = H_0 + V_{np} + U_{pA} + U_{nA}}$$  

- Faddeev equations are the rigourous way to solve the three-body problem. L. D. Faddeev, Zh. Eksp. Teor. Fiz. 39, 1459 (1960).

- Most commonly solved in the momentum space and well known as **Faddeev-AGS** equations. E. O. Alt, P. Grassberger, and W. Sandhas., Nucl.Phys. B 2 (1967) 167

<div class="grid grid-cols-2 gap-5 items-center justify-center">
<div class="col-span-1 text-center">
<img src="/pics/Faddeev-AGS.png" alt="Description" class="w-180 h-80 object-contain">
</div>
<div class="col-span-1 text-center">
<v-click>

$$U^{ij}=\bar\delta_{ij} G_0^{-1}(E)+\sum_k\bar\delta_{ik}\color{#FF2600}{t_k}\color{#000000}{G_0(E)U^{kj}}$$

$$U^{0j}=G_0^{-1}(E)+\sum_k \color{#FF2600}{t_k}\color{#000000}{G_0 U^{kj}}$$
</v-click>

<v-click>

<span style="color:#FF2600;">two body t-matrix: $t_k=v_k+v_kg_ot_k$</span>
</v-click>

<v-click>

Observables: $\sigma_{i\gets j} \propto |\langle \Phi_i|U^{ij}|\Phi_j \rangle |^2$
</v-click>

More details can be found in: <span style="color:#0076BA;">L. Hlophe, **JL** et al, Phys. Rev. C 96, 064003 (2017), Phys. Rev. C 100, 034609 (2019), and **JL**, L. Hlophe et al, Phys. Rev. C 98, 051001 (2018)</span>

</div>
</div>

---
layout: pageBar
---

# Modeling the Reaction in three-body model 
More degree of freedom invloved, can be used to study transfer and breakup reactions

- Solving the **three-body** Schrodinger equation：**two-body** projectile with inert cores on inert target (take d+A system as an example)

$$E|\Psi\rangle =H |\Psi\rangle   \ \ \ \ \ \color{#FF2600}{\to}   \ \ \ \ \ \color{#000000}{H = H_0 + V_{np} + U_{pA} + U_{nA}}$$  

- Faddeev equations are the rigourous way to solve the three-body problem. L. D. Faddeev, Zh. Eksp. Teor. Fiz. 39, 1459 (1960).

- Can also be solved in the coordinate space, e.g. **Faddeev-Merkuriev** equations. Naturally suited for Coulomb interactions. 

<v-click>

$$
\Psi=\psi_{ij}+\psi_{jk} +\psi_{ki}, 
$$
</v-click>
<v-click>

$$
\begin{align}
(E-H_0-V_{ij}-W_k) \psi_{ij} &= V_{ij}^S (\psi_{jk}+\psi_{ki}), \nonumber \\
(E-H_0-V_{jk}-W_i) \psi_{jk} &= V_{jk}^S (\psi_{ij}+\psi_{ki}),\nonumber \\
(E-H_0-V_{ki}-W_j) \psi_{ki} &= V_{ki}^S (\psi_{ij}+\psi_{jk}),\nonumber
\end{align}
$$
</v-click>

<v-click>

- By the **complex scaling method**, one can simutaneously solve the bound and scattering states in the same framework.
</v-click>
<v-click>

- Preparing a new computer code to solve the Faddeev-Merkuriev equations for identical particles, including bound and scattering states. The code, written in Julia, is named **S**cattering **W**ith **I**dentical **F**addeev **T**hree-Body Solver (**SWIFT.jl**). <span style="color:#0076BA;"> ***JL**, preparing for submission*.</span>

- For those interested, please have a look at the code: <a href=https://github.com/jinleiphys/swift.jl>SWIFT.jl</a>
</v-click>

---
layout: pageBar
---

# Modeling the Reaction in three-body model 
More degree of freedom invloved, can be used to study transfer and breakup reactions

- Solving the **three-body** Schrodinger equation：**two-body** projectile with inert cores on inert target (take d+A system as an example)

$$E|\Psi\rangle =H |\Psi\rangle   \ \ \ \ \ \color{#FF2600}{\to}   \ \ \ \ \ \color{#000000}{H = H_0 + V_{np} + U_{pA} + U_{nA}}$$  

- Faddeev equations are the rigourous way to solve the three-body problem. L. D. Faddeev, Zh. Eksp. Teor. Fiz. 39, 1459 (1960).

- However, the **Faddeev equations** are computationally intensive and thus unsuitable for weakly bound projectiles, such as $^{11}$Be, $^{6}$Li, and $^{8}$B.

<v-click>

- The continuum discretized coupled channels (**CDCC**) method is a widely used alternative. It is based on the expansion of the continuum states in a discrete basis, which allows for the treatment of weakly bound projectiles.
</v-click>
<v-click>

$$
\left(E-\varepsilon_n-T_{a A}(R \alpha)\right) \langle\phi_{b x}^n R \alpha| \Psi^{j_{\mathrm{jin}}(+)} \rangle - \sum_{\alpha^{\prime}n'} \langle \phi_{b x}^n R \alpha| U_{pA}+U_{nA}| \phi_{b x}^{n'} R \alpha' \rangle \langle\phi_{b x}^{n^{\prime}} R \alpha^{\prime}| \Psi^{j_{\mathrm{in}}(+)} \rangle = 0,
$$
</v-click>

<v-click>

- We have developed a new computer code, the **S**hanghai **T**ongji **A**dvanced **R**eaction **S**olver (**STARS**), to solve the CDCC equations. Unlike the well-known code **FRESCO**, **STARS** employs the **R-matrix method**, solving **linear equations** rather than differential equations. It naturally incorporates **nonlocal potentials** and is easily extensible to methods such as **eigenvector continuation**. <span style="color:#0076BA;">*H. Liu, **JL**, Z. Ren, in preparation for submission*.</span>
</v-click>

---
layout: pageBar
---

# Breakup reactions of weakly bound projectiles
Exclusive and inclusive breakup reactions

Take $^6$Li as example

Exclusive breakup:
<div class="grid grid-rows-1 gap-8 h-full items-center justify-center">
  <div class="text-center">
    <img src="/pics/dA_chans_exclusive.png" alt="Exclusive breakup channels" class="w-180 h-120 object-contain mx-auto">
  </div>
  
</div>

---
layout: pageBar
---

# Breakup reactions of weakly bound projectiles
Exclusive and inclusive breakup reactions

Take $^6$Li as example

Inclusive breakup:


<div class="grid grid-rows-1 gap-8 h-full items-center justify-center">  
  <div class="text-center">
    <img src="/pics/dA_chans_inclusive.png" alt="Inclusive breakup channels" class="w-280 h-120 object-contain mx-auto">
  </div>
</div>

---
layout: pageBar
---

# Breakup reactions of weakly bound projectiles
Experimental examples 

<div class="grid grid-cols-2 grid-rows-3 gap-4 h-4/5 w-full p-4">
  
  <!-- 第一张图片：占用2行1列 -->
  <div class="row-span-2 col-start-1 flex items-center justify-center">
    <img src="/pics/Li6inclusive.png" class="w-180 h-80 object-contain" />
  </div>
  
  <!-- 第二张图片：占用2行1列 -->
  <v-click>
  <div class="row-span-2 col-start-2 flex items-center justify-center">
    <img src="/pics/surrogate.png" class="w-180 h-80 object-contain" />
  </div>
  </v-click>
  
  <!-- 第三张图片：占用1行1列 -->
  <v-click>
  <div class="row-start-3 col-start-1 flex items-center justify-center">
    <img src="/pics/knockout.png" class="w-180 h-36 object-contain" />
  </div>


  <!-- 文字内容：占用1行1列 -->
  <div class="row-start-3 col-start-2 flex flex-col justify-center p-4">
    <h3 class="text-lg font-bold mb-2">Knockout reaction</h3>
    <ul class="text-sm space-y-1">
      <li>• Study the Spectroscopic factor</li>
      <li>• Current theory based on eikonal approximation (semi-classical)</li>
      <li>• Fully quantum model is needed</li>
    </ul>
  </div>
  </v-click>
  
</div>

---
layout: pageBar
---

# The Ichimura-Austern-Vincent (IAV) model
A fully quantum mechanical model for the breakup reactions. (M. Ichimura, N. Austern, and C. M. Vincent, PRC 32, 431 (1985))

Inclusive breakup :
$$
a + A \to b + B^* ,
$$
where $a = b + x$ represents the two-body structure of the projectile, $B^*$ denotes any possible state of the $x + A$ subsystem. This can include the elastic state, where both $x$ and $A$ are in their ground states, or nonelastic states, which involve particle exchange between $x$ and $A$, inelastic scattering of $x + A$ where either $x$ or $A$ is in an excited state, or the formation of compound nuclei by $x$ and $A$. The former is called **elastic breakup**, and the latter is called **nonelastic breakup**.

<v-click>

In IAV model, the inclusive breakup cross section is given by:
$$
\frac{d^2\sigma}{dE_bd\Omega_b}=-\frac{2}{\hbar v_a} \rho_b (E_b) 
\mathrm{Im} \langle \rho(\vec{k}_b) |G_x^{(+)}| \rho(\vec{k}_b)\rangle
$$

where the **elastic breakup** double differential cross section is given by:
$$
\frac{d^2\sigma}{dE_b d\Omega_b}\Big|_\mathrm{EBU}= \frac{2\pi}{\hbar v_a} \rho_b(E_b)   \rho_x(E_x)   \int \bigg| \langle \chi^{(-)}_{x} (\vec{k}_x) | \rho(\vec{k}_b)  \rangle \bigg|^2
d\Omega_{k_x}
$$
and the **nonelastic breakup** double differential cross section is given by:
$$
\frac{d^2\sigma}{dE_b d\Omega_b}\Big|_\mathrm{NEB}= -\frac{2}{\hbar v_a} \rho_b(E_b) 
\langle G_x^{(+)}\rho(\vec{k}_b) |W_x|  G_x^{(+)}\rho(\vec{k}_b) \rangle
$$
</v-click>

---
layout: pageBar
---

# Application of the IAV model for deuteron breakup reactions
A new computer code, **S**cattering **M**odel of **O**ptical **O**perator **Th**eory for **I**chimura-Austern-Vincent **E**quations (**SMOOTHIE**), has been developed to compute the nonelastic breakup cross sections.

The IAV model aligns well with the semi-classical Glauber model with quantum $S$-matrix predictions, both matching experimental data effectively. 

More details can be found in *H. Liu, S. Nakayama, **JL**, and Z. Ren, Phys. Rev. C 108, 014617 (2023)*
<div class="flex justify-center gap-6 mt-8">
  <v-click>
    <img src="/pics/Ni56dpxall.png" alt="d + 93Nb scattering" class="w-128 h-98 object-contain">
  </v-click>
  
  <v-click>
    <img src="/pics/dnx.png" alt="6Li + 208Pb scattering" class="w-128 h-94 object-contain">
  </v-click>
  
  <!-- <v-click>
    <img src="/pics/n56Fe.png" alt="n + 56Fe scattering" class="w-72 h-48 object-contain">
  </v-click> -->
</div>


---
layout: pageBar
---

# Surface approximation in the IAV model
Testing the semi-classical perspective using asymptotic $S$-Matrix calculations

- In the Glauber model, the inclusive breakup cross section is typically computed using the $S$-matrix approximation, which assumes that the scattering wave function can be expressed as:
$$
u_l(r)  \approx \frac{i}{2}\left [ H^{(-)}_l(r)-S_lH^{(+)}_l(r) \right ]
$$

<v-click>
- However, due to the irregularity of this asymptotic form at the origin, we introduce a radial cut-off to the scattering wave functions both in the entrance and the exit channel consistently
$$
u_{l_a}(r)=u_{l_b}(r)=0   \qquad r<R_{\mathrm{cut}},
$$
</v-click>

<div class="grid grid-cols-3 justify-center gap-6 mt-8">
 <v-click>
<div class="col-span-1">
<img src="/pics/sla100.png" alt="d + 93Nb scattering" class="w-128 h-60 object-contain">
</div>
</v-click>
<v-click>
<div class="col-span-1">
<img src="/pics/dsla.png" alt="6Li + 208Pb scattering" class="w-128 h-60 object-contain">
</div>
</v-click>
<v-after>
<div class="col-span-1 flex items-center justify-center text-center">
 More details can be found in J. Liu, JL, and Z. Ren, Phys. Rev. C 108, 024606 (2023)
</div>
</v-after>
</div>

---
layout: pageBar
---

# Extending the IAV Model with CDCC Wave Functions
Examining the Validity of the DWBA Form

<!-- - The original IAV model is based on the Distorted Wave Born Approximation (DWBA), which assumes that the breakup wave function can be approximated by a single-particle wave function. However, this assumption may not hold for weakly bound projectiles, where the breakup process involves more complex dynamics.  -->



- We have extended the IAV model to include the CDCC wave functions, which account for the continuum states of the projectile. This allows for a more accurate description of the breakup process, especially for weakly bound projectiles.
$$
\Psi^{3 b(+)} \simeq  \Psi^{\mathrm{CDCC}(+)}\left(\mathbf{r}_a, \mathbf{r}_{b x}\right) 
=  \sum_i \phi_a^i\left(\mathbf{r}_{b x}\right) \chi_a^{i(+)}\left(\mathbf{r}_a\right) 
 +\sum_c^N \phi_a^c\left(k_c, \mathbf{r}_{b x}\right) \chi_a^{c(+)}\left(K_c, \mathbf{r}_a\right),
$$

<v-click>

The term $\color{#FF2600}\phi_a^0\left(\mathbf{r}_{b x}\right) \chi_a^{0(+)}\left(\mathbf{r}_a\right)$ can be consider as the DWBA term, while the left terms take the higher order effects into account.
</v-click>

<div class="grid grid-cols-3 justify-center gap-6 mt-8">
 <v-click>
<div class="col-span-1">
<img src="/pics/d93nb.png" alt="d + 93Nb scattering" class="w-128 h-60 object-contain">
</div>
</v-click>
<v-click>
<div class="col-span-1">
<img src="/pics/li6cdcc_dwba.png" alt="6Li + 208Pb scattering" class="w-128 h-60 object-contain">
</div>
</v-click>
<v-after>
<div class="col-span-1 flex items-center justify-center text-center">
 More details can be found in JL, and A.M. Moro, Phys. Rev. Lett. 123, 232501 (2019); Phys. Rev. C 108, 034612 (2023)
</div>
</v-after>
</div>


---
layout: pageBar
---

# Conclusions 

<div class="h-full flex flex-col justify-center space-y-6">


<v-click>

- Developed **COLOSS** code for elastic scattering with complex scaling method
  - Successfully handles Coulomb + nuclear potentials
  - Validated against experimental data for various systems
</v-click>

<v-click>

- Implemented **eigenvector continuation** for efficient emulation of reaction observables
  - <span style="color:#FF2600;">100× faster</span> than direct calculations
  - Enables uncertainty quantification in optical potentials
</v-click>

<v-click>

- Developed **SWIFT.jl** code for identical particle Faddeev calculations in coordinate space using complex scaling
  - Solves bound and scattering states simultaneously
</v-click>
<v-click>

- Created **STARS** code for CDCC calculations using R-matrix method
  - Natural incorporation of nonlocal potentials
  - Extensible to advanced methods
</v-click>

<v-click>

- Developed **SMOOTHIE** code for inclusive breakup reactions using IAV model
  - Consistent with Glauber model and quantum $S$-matrix predictions
  - Validated against experimental data for various systems
  - Extended **IAV model** with CDCC wave functions for inclusive breakup
</v-click>

</div>

---
layout: pageBar
---

# Acknowledgments

<div class="h-full flex flex-col justify-center">

<div class="text-2xl space-y-8">

### Collaborators:
- **J. Liu** (Tongji University)
- **H. Liu** (Tongji University)  
- **Z. Ren** (Tongji University)
- **A.M. Moro** (Universidad de Sevilla)


### Funding Support:
- National Natural Science Foundation of China
- Fundamental Research Funds for the Central Universities

<v-click>

<div class="text-center mt-12 text-3xl" style="color:#4A9CF7;">
Thank you for your attention!
</div>



<div class="text-center mt-6 text-xl">
Questions and discussions are welcome
</div>
</v-click>
</div>

</div>