# Cellar management package

## About the cellar management package

This project has been developed as part of my data science training, so its main reason for being was for me to pratice my object-oriented development. The package has been designed to help with the management of a wine cellar. It is meant to help with keeping track of bottles in ones cellar and to be able to easily find some bottles based on specific characteristics.

## Links
https://github.com/Granju/cellar-management-package.git hosts the package on github.
https://pypi.org/project/cellar-management/ is the address of the package on PyPI.

## Installing the package

The package is available on PyPI can be installed by running the following command in your terminal:

```
pip install cellar_management_package

```

## Files
bottle.py is used to create a bottle class and its associated methods.
cellar.py is used to create a cellar class and its associated methods. Bottle class objects are meant to be stored in a list attribute of cellar objects.

## Examples
Here is a list of wines that can be saved as a txt file to be used by the read_data_file cellar method:
```
red,Saint Desirat,Saint Joseph,2015,2020,2030
red,Saint Desirat,Saint Joseph,2015,2020,2030
red,Saint Desirat,Saint Joseph,2015,2020,2030
red,Saint Desirat,Saint Joseph,2015,2020,2030
red,Saint Desirat,Saint Joseph,2015,2020,2030
white,Saint Desirat,Viognier,2015,2020,2021
white,Saint Desirat,Viognier,2015,2020,2021
white,Saint Desirat,Roussane,2015,2025,2030
red,DRC,Romane Conti,2008,2008,2028
red,DRC,Romane Conti,1986,1988,2011
sparkling,Krug,Speciale cuvee,2005,2012,2027
sparkling,Krug,Speciale cuvee,2005,2012,2027
rose,Clos Cibonne,Côtes de Provence Rosé Cru Classé ‘Tradition’,2020,2020,2025
rose,Clos Cibonne,Côtes de Provence Rosé Cru Classé ‘Tradition’,2020,2020,2025
rose,Clos Cibonne,Côtes de Provence Rosé Cru Classé ‘Tradition’,2020,2020,2025
white,Chateau de Fosse Seche,Arcane,2021,2021,2030
red,Chateau de Fosse Seche,Gondwana,2021,2025,2040
red,Chateau de Fosse Seche,Gondwana,2021,2025,2040

```
Here is an example python script to showcase usage of the package:
```
from cellar_management import bottle, cellar

cellar_ju = cellar(20)

print('\n Adding bottles from a txt file:')
cellar_ju.read_data_file('wines.txt')

cellar_ju.show()

print('\n Finding passed bottles in the cellar:')
cellar_ju.subset('maturity', 'old').show()

print('\n Attempting to remove more bottles than present in the cellar:')
cellar_ju.remove(bottle(white,Saint Desirat,Roussane,2015,2025,2030),2)

print('\n Attempting to add more bottles than possible in the cellar:')
cellar_ju.remove(bottle(white,Saint Desirat,Roussane,2015,2025,2030),10)

```


## License

This package is released under the MIT licsense. See the license.txt file more details.
