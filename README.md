# To-Plot-Mohr-Circle-Diagram
Calculation of plane stress and shear stress to draw a mohr circle of radius R 
#python code to draw/create mohr circle with python program
import numpy as np
import matplotlib.pyplot as plt
s_x = int(input("Enter Plane Stress at X-Axis:") )
s_y = int(input("Enter Plane Stress at Y-Axis:") )
t_xy = int(input("Enter Shear Stress Value:"))

theta = np.linspace(0,2*np.pi,360)

s_avg = (s_x +s_y)/2
R = np.sqrt((0.5*(s_x - s_y))**2 + t_xy**2)
x = s_avg + R*np.cos(theta)
y = R*np.sin(theta)

plt.plot(x,y) #mohr circle
plt.plot([s_avg-R-10,s_avg+R+10],[0,0],linestyle='--',color='black') #dash line horizontal
plt.plot([s_avg,s_avg],[-R-10,R+10],linestyle='--',color='black') #dash line vertical
plt.plot([s_x,s_y],[-t_xy,t_xy],[s_x,s_x],[-t_xy,0],[s_y,s_y],[t_xy,0],linestyle='--',color='green') #cross bar and other 2 percendicular

plt.title('Mohr Circle')
plt.xlabel(r'$\sigma$')
plt.ylabel((r'$\tau$'))

plt.plot()
plt.show()
