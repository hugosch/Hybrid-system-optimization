# Optimisation of Hybrid PV-FUEL Off-grid System using Oemof and PVLib 

This project was made to evaluate the impact of not using storage in an Off-Grid Hybrid System. 

The PV production was generated with real meteorological data from www.soda-pro.com and using the library PVLib (see PV-Production.ipynb).

Then, the optimisation of the system was made with the Library Oemof. The final results give the you the size of the PV power plant, the dispatching of the different electricity production and consumption at the lower cost.

![84230623_186638612665648_7407903293709484032_n](/home/hugosch/Documents/MS ENR/Project/Results/84230623_186638612665648_7407903293709484032_n.png)





## Getting Started 

To run the project you need to install :

```
pip install pvlib
```

```
pip install oemof
```

You need a solver with Oemof, we used **cbc**

```
https://github.com/coin-or/Cbc
```

## PV-Production.ipynb

To run this notebook, you will need to download Merra-2 and CAMS radiation data from soda-pro.

Then, run the function **prod** 

If you want to get the best tilt for a better production throughout the year, use **definetilt**

To get 12 representative days (one for each month), use **get12days**

And to format the .csv file to use it in Oemof, use **file4oemof**

## Oemof optimization.ipynb

To run this notebook, you first need a file with :

- Demand (in kW)
- PV production (normalised)

Use the notebook **PV-Production.ipynb** to get it 

Run the function **optilgen** the use Oemof

If you want the best number of generator, use the function **bestngen**



*Note : If your first generator doesn't give enough power to respond to the demand the program won't work* 

# Results :

![DemandeVariablediesel](/home/hugosch/Documents/MS ENR/Project/Results/DemandeVariablediesel.png)



## Built with :

1. **pvlib-python** - a set of documented functions for simulating the performance of a photovoltaic system located  @https://github.com/pvlib/pvlib-python
2. **oemof **- Open Energy Modelling Framework - Base packages for energy system modelling and optimisation @https://github.com/oemof/oemof
3. **Soda-pro** - Solar radiation data @http://soda-pro.com/
4. **CBC** - COIN-OR Branch-and-Cut solver @https://github.com/coin-or/Cbc

## Authors

- Hugo Schoen
- Cécile Gnouloufoum
- Pablo Zamorano
- Antoine Ribes