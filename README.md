# Ethereum Simulation Analysis

# Goal
Ethereum introduced EIP 1559 which brought many changes to how ethereum worked. One of the big changes was that transactions included a basefee. Since there were already assumptions about how basefee might behave, simulations could be created and compared to actual basefee behavior to try and verify if the original assumptions were correct. Interestingly enough, aside from verifying assumptions, many other discoveries were found in the simulation analysis. 

# Assumptions 
* Variables that we wanted to model were demand, valuation and gas used 
* Base follows the following update function which will be explained later: <img src="https://latex.codecogs.com/svg.image?b_{n&plus;1}=b_n(1&plus;\frac{1}{d}*\frac{g_n-g_{target}}{g_{target}})" title="b_{n+1}=b_n(1+\frac{1}{d}*\frac{g_n-g_{target}}{g_{target}})" />
