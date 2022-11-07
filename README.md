(# Assignment-9)
import numpy as np
import matplotlib.pyplot as plt
rop = 2650.0 # density of particle in kg/m3
rof = 1000.0 # density of water in kg/m3
visc = 1.002*1E-3 # dynamic viscosity in Pa*s at 20 C
C1 = 18 # constant in Ferguson-Church equation
C2 = 1 # constant in Ferguson-Church equation
def v_stokes(rop,rof,d,visc,C1):
        R = (rop-rof)/rof # submerged specific gravity
        w = R*9.81*(d**2)/(C1*visc/rof)
        return w
def v_turbulent(rop,rof,d,visc,C2):
        R = (rop-rof)/rof
        w = (4*R*9.81*d/(3*C2))**0.5
        return w
def v_ferg(rop,rof,d,visc,C1,C2):
        R = (rop-rof)/rof
        w = ((R*9.81*d**2)/(C1*visc/rof+
            (0.75*C2*R*9.81*d**3)**0.5))
        return w
