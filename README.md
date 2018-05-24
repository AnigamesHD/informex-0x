# informex-0x#<strong>Trabajo Práctico Nº6: Visualización de proteinas usando VMD</strong>

#BIT120

__Laboratorio de Bioinformática__


                                                                


---

####<strong>Responde:
####1. Señale el método experimental por el cuál se resolvió la estructura de la proteina 1OS1 y la resolución que tiene.
#####R.- Luego de descargar la proteina 1OS1 desde PDB en formato .pdb, se prosiguió a abrir el archivo utilizando WordPad, donde se muestra la información referente a esta; por lo que si se recurre al registro EXPDTA (técnica experimental utilizada), el método experimental fue de difracción por rayos X (X-ray diffraction). 
####2. Identifique las moléculas cristalizadas en el PDB.
#####R.- Si ahora se recurre a la sección de más abajo hacia las moléculas que fueron cristalizadas, puede observarse que se muestra agua, piruvato, ATP, proteinas, magnesio, carbono α.
####3. Identificar aminoácidos cercanos (4 angstrom) al residuo 20 de la proteina. Señalar código de 3 letras y número de residuo del aminoácido.
#####R.- Mediante el programa VMD, y luego de cargar la proteina descargada de PMD, para poder identificar los aminoácidos cercanos al residuo 20 y a 4 Å de  distancia, en "Selected atoms" se colocó "protein and same residue as within 4 of resid 20", con ResID para Coloring method y Licorice para Drawing method, y asi obtener una mejor resolución de los aminoácidos visualizados.

![Texto Alternativo](http://image.prntscr.com/image/458d7a3856b845b58a4d150519035d03.png)

#####Al presionar la tecla 1 para obtener las características especificas del átomo y luego de hacer click en cada residuo, obteniendo su código a través de la consola de VMD, se identificaron los aminoácidos: LYS116, HIS21, SER18, PRO9, VAL20, ASP22, ASP19, LEU17, LEU118.
 
####4. Señale el número de moléculas de agua del sistema si las hubiese.
#####R.- Para obtener el número de moléculas de agua, se recurre a la extensión Tk Consola de VMD, donde se ejecuta el script: set agua [atom select top "water"], indicando el nombre "agua" para la variable a guardar. Luego para saber el número de moléculas de agua, se coloca $agua num, donde el signo $ es para llamar a la variable, y num para saber el número de esta variable. Al colocar el comando, se llega a que existen 260 moléculas de agua en el sistema. 

####5. ¿Cuál es el centro de la molécula de ATP?
#####R.- Para localizar el centro de una selección, y luego de llamar a la variable como set ATP [atomselect top "resname ATP"], para localizar el centro entonces el comando es measure center $ATP. De donde se obtienen las coordenadas: 

#####X= 28.141870498657227
#####Y= 10.711871147155762
#####Z= 13.21480655670166
                                                                                   
####6. Indique el tamaño (x,y,z) de todo el sistema.
#####R.- Para indicar que se trata de todo el sistema, se coloca como set todo [atomselect top "all"], y para obtener las coordenadas para el tamaño del sistema, se coloca entonces measure center $todo. De este comando, se obtienen las coordenadas: 

#####X1= -4.01800012588501
#####Y1= -27.242000579833984
#####Z1= -19.19300079345703

#####X2= 69.56400299072266
#####Y2= 29.253999710083008
#####Z2= 37.26100158691406

#####Donde el tamaño final del sistema viene dado por la diferencia entre los ejes, quedando como:

#####X=(X2-X1)=(69.56400299072266+4.01800012588501)= 73.582003112
#####Y=(Y2-Y1)=(29.253999710083008+27.242000579833984)=56.49600028
#####Z=(Z2-Z1)=(37.26100158691406+19.19300079345703)=56.45400237

###<strong>-Scripts ejecutados en Tk Consola

![Texto Alternativo](http://image.prntscr.com/image/d98d545218da4905beec05b729fe7e8f.png)

####7. ¿Cuáles son los aminoácidos ubicados a 3 Å de la molécula PYR?
#####R.- Volviendo a la representación gráfica de VMD, en "Selected atoms" se coloca "protein and same residue as within 3 of resname PYR" para saber qué aminoácidos están ubicados a una distancia de 3 Å de la molécula PYR, obteniendo dos residuos: TYR207 y ARG65.

![Texto Alternativo](http://image.prntscr.com/image/82aa872cabd14233a6fda951e81e445a.png)

####8. Señale la distancia entre los carbono alfa (CA) de los aminoácidos Gln34 y Thr8.
#####R.- Para que se muestren sólo esos aminoácidos, se coloca "resid 34 8", y luego se encuentra y selecciona el carbono alfa de cada uno. Para obtener la distancia entre ellos, se selecciona la tecla 2 y los CA, mostrando una distancia de 23,61 Å, y de forma más precisa al revisar la consola de VMD: 23,609707.

![Texto Alternativo](http://image.prntscr.com/image/7107f47f76de448db4f5ff5818c2afdc.png)
 
####9. Indique la descripción (name, type, index, residue, resname, resid, chain, x, y, z) del átomo "serial 3391".
#####R.- Retornando al archivo .bpm en WordPad, al buscar el átomo 3391, se tiene que se trata del residuo 443, por lo que en el programa de VMD al colocar resid 443, y seleccionar la ubicación del aminoácido de 3391, se obtiene que:

#####name: NE1
#####type: NE1
#####index: 3390
#####residue: 439
#####resname: TRP
#####resid: 443
#####chain: A
#####x: 23.735001
#####y: 19.156000
#####z: 6.034000

![Texto Alternativo](http://image.prntscr.com/image/8afa01921b1543d18d54bd65536472db.png)

####10. Indique qué ion se encuentra más cercano al ATP y señale las distancias correspondientes (Considerar el último fosforo del ATP name PG).
#####R.- Se coloca esta vez "resname ATP", luego Create rep para agregar otra representación como "ions". Se observan dos iones cercanos a la molécula de ATP, por lo que se ubica el último fosforo de su cadena de nombre PG (ATP541:PG), y entonces para medir la distancia, se presiona la tecla 2 y luego se seleccionan ambos iones. 

![Texto Alternativo](http://image.prntscr.com/image/99cc7237e78e4af6bfdfb01cbc438220.png)

#####Los iones corresponden a MG998, con una distancia de 3.73 Å respecto del ATP; y el otro a CA999, con una distancia de 3.56 Å del ATP, por lo que este último se encuentra más cercano a la molécula.
