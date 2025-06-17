---
# You can also start simply with 'default'
theme: hep
preTitle: "Nuclear Reaction Studies Using Weakly Bound Projectiles: Structure and Dynamics"
authors:  # First author should be the presenter
  - Jin Lei: ["School of Physics Science and Engineering, Tongji University, Shanghai 200092, China."] 
meeting: "xXX"

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

- We developed a new computer code, **COLOSS**, using the complex scaling method to compute elastic scattering cross sections
  
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

- Preparing a new computer code to solve the Faddeev-Merkuriev equations for identical particles, including bound and scattering states. The code, written in Julia, is named **Scattering with Identical Faddeev Three-Body Solver** (SWIFT.jl). <span style="color:#0076BA;"> ***JL**, prepraing for submission*.</span>

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

- We have developed a new computer code, the Shanghai Tongji Advanced Reaction Solver (**STARS**), to solve the CDCC equations. Unlike the well-known code **FRESCO**, **STARS** employs the **R-matrix method**, solving **linear equations** rather than differential equations. It naturally incorporates **nonlocal potentials** and is easily extensible to methods such as **eigenvector continuation**. <span style="color:#0076BA;">*H. Liu, **JL**, Z. Ren, in preparation for submission*.</span>
</v-click>