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
