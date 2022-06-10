# Preliminary-design-of-a-gas-turbine-combustor-using-EES
A simple program that calculates the Primary, Secondary and Dilution air mass flows needed to obtain the maximum tolerated temperature in our combustion products
As well as calculating the total NO emission of the combustor (in ppm)
Run all 3 programs with the Solve(F2) button. No parametric tables were used in any of the programs. Here is a brief overview of every program.
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
Part 1 - a:
Code relating to the complete combustion assumption of the first segment of the preliminary design. (Problem 1)
Important variables: 
m_dot_1                   Primary air mass flowrate
m_dot_2                   Secondary air mass flowrate
m_dot_3                   Dilution air mass flowrate
a[i]                      The mole count of O2 in our reactants PER 1 MOLE OF FUEL
                          Note that for every variable that is in a array (such as this one), I have split the problem into 3 different runs:
                          Every variable with a [1] subscript is the value of that variable at the end of ER1
                          Every variable with a [2] subscript is the value of that variable at the end of ER2, as if ER1   and ER2 were both taken as a single control volume
                          Every variable with a [3] subscript is the value of that variable at the end of ER3, as if ER1, ER2 and ER3 were both taken as a single control volume
b[i],c[i],d[i],e[i],f[i],g[i],j[i],k[i],m[i],n[i]                Mole count of the different product species PER 1 MOLE OF FUEL
n_tot[i]                  Total mole count of our product species PER 1 MOLE OF FUEL
y_()[i]                   Mole fractions of the different product species 


Part 1 - b:
Code relating to the incomplete combustion assumption of the first segment of the preliminary design. (Problem 2)
Important variables: 
K_1[i] up until K_6[i]                Equilibrium constant



Part 2:
Code relating to the second segment of the preliminary design.
Important variables: 
PPM                       Total NO emission of the combustor in ppm
C_NO[z]                   The NO concentration at each stage of the combustor
                          C_NO[1] is the value of the concentration after ER1 but before PFR1
                          C_NO[2] is the value of the concentration after ER2 but before PFR2
                          C_NO[3] is the value of the concentration after ER3 but before PFR3
                          C_NO[4] is the value of the concentration after PFR3, which also is the value of the concentration at the outlet of the entire combustor system
dC_NOdt[z]                The rate of change of the NO concentration at each stage of the combustor
C_()[z]                   The concentration of the relevant product species at each stage of the combustor
rho[z]                    The density of the entire mixture at each stage of the combustor
t_r[z]                    The residence time at each PFR
v[z]                      The speed of the mixture at each PFR
m_dot_cumulative[z]                         The total mass flowrate for air AND fuel at each stage of the combustor
RR_1[z] up until RR_2[z]                    The Rate of Reaction for the each of the reactions in the Zeldovich mechanism
k_N1_f[z] up until k_N3_f[z]                The forward Rate Coefficients for the each of the reactions in the Zeldovich mechanism
k_N1_r[z] up until k_N3_r[z]                The reverse Rate Coefficients for the each of the reactions in the Zeldovich mechanism
~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
