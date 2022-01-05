# Ethereum Simulation Analysis

# Goal
Ethereum introduced EIP 1559 which brought many changes to how ethereum worked. One of the big changes was that transactions included a basefee. Since there were already assumptions about how basefee might behave, simulations could be created and compared to actual basefee behavior to try and verify if the original assumptions were correct. Interestingly enough, aside from verifying assumptions, many other discoveries were found in the simulation analysis. 

# Assumptions 
* Variables that we wanted to model were valuation and gas used 
* Miners accept highest bids first
* Base follows the following update function which will be explained later: 
<img src="https://latex.codecogs.com/svg.image?b_{n&plus;1}=b_n(1&plus;\frac{1}{d}*\frac{g_n-g_{target}}{g_{target}})" title="b_{n+1}=b_n(1+\frac{1}{d}*\frac{g_n-g_{target}}{g_{target}})" />

# Valuations 
Definition: Valuations is an economic term which means how much a good is worth to a person. 

In the most simple scenario, this means a valuation can be found by how much a person is willing to pay for a good. However, the data team I worked with was also interested in how valuations change both pre- and post-EIP 1559. So simply using the highest bid would not be sufficient in this case. 

Solution: 
In order to try and tease out a users valuation, we took their bids and divided it by a common reccommended bid provided by Go Ethereum (GETH). Most users of Ethereum will see the GETH recommended bid as they are putting in their transactions so how they bid relative to GETH recommendation is a good indicator of their valuation. Mathmatically, we defined valuations as (user's bid)/(GETH recommended bid) 

![image](https://user-images.githubusercontent.com/85899973/148271912-eaa13a58-830c-45ee-99d5-dcf8c34eb1ca.png)
