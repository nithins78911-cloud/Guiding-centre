# Guiding_Centre
**Abstract** : 
          This program implements the guiding-centre(gyro centre) of the single charged particle subjected to the static and non-uniform magnetic field. Given the particles intitial conditions such as intitial position, velocity and ambient magnetic field vector, this program computes the guiding centre displacement analytically and reports the larmor-radius offset value (used the approximation from the micro-particles dynamics in plasma physics).

**Theoretical Background :** 
            in the guiding-centre approximation, valid when the larmor radius is small relative to the spatial scale over which the magnetic field varies, and the instantaneous position of a charged particle in the magneitc field is decomposed into particle's guiding centre position and circular gyration about that centre and for the particle with charge q and mass m in a uniform field B, the guiding-centre position is given by:

               $$\mathbf{R}_{gc} = \mathbf{r} + \frac{m}{q\,B^2}\,(\mathbf{v} \times \mathbf{B})$$   

where r is the instantaneous particle position and v is its velocity. The displacement term ( m / (q * B^2) ) * (V * B) represents the gyroradius vector , whose magnitude equals the Larmor radius :

            $$\mathbf{R}_{gc} = \mathbf{r} + \frac{m}{q\,|\mathbf{B}|^2}\,(\mathbf{v} \times \mathbf{B})$$   

**Implementation :**
The program is written in standard Fortran and proceeds as follows:
 1. The user supplies the initial position vector r (m), velocity vector v (m s⁻¹), and magnetic field vector B (T) via standard input.
 2. The cross product v × B is computed component-wise.
 3. The guiding-centre position R_gc is evaluated from the closed-form expression above.
 4. The Larmor-radius offset along the y-axis, Δy=Rgc,y​−ry​, is reported as a diagnostic quantity.

**Assumptions and Limitations:**

  1.The magnetic field is assumed uniform and time-independent.
  2.The particle is assumed to carry a positive elementary charge (proton).
  3.No electric field or gravitational forces are included.
  4.The guiding-centre approximation is strictly valid only in the limit ρ_L​≪ L_B​, where L_B​ is the magnetic-field gradient      scale length.


## Compilation and Execution

**Prerequisites:** GNU Fortran compiler (`gfortran`) version 4.0 or later.

```bash
gfortran guiding_Centre.f90 -o guiding_centre
./guiding_centre

**Notes:**
 1. The .f90 extension must match your file name exactly (case-sensitive on Linux/macOS).
 2. On Windows, replace ./guiding_centre with guiding_centre.exe..



                                       

