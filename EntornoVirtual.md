# Crear un Entorno Virtual

Si deseas crear un entorno virtual entonces muy posiblemente querras trabajar desde algun servidor remoto o quizás no quieres que se _'crucen los cables'_ de tus librerias. Usualmente vamos a querer usar nuestros entornos virtuales para **conda**, aquí te dejamos un tutorial paso a paso de como hacerlo.

### Conda
Asegurate de tener instalado el gestor de paquetes **conda** en tu maquina antes de iniciar este tutoral, si no aún no lo tienes aquí te enseñamos como. 

> [!NOTE]
>
> Aquí deberia agregar un link o algo para la instalacion de conda en una maquina virtual. 


### Entorno Virtual
Ya instalado el gestor de paquetes en tu maquina, asegurate tener un archivo ___YAML___ , los archivos _.yml_ son de un lenguaje de serializacion de datos muy común en el diseño de archivos de configuracion. 

YAML te ayudará a establecer de base la configuracion de tu entorno, donde podrás especificar que tipos librerias vas a utilizar y especificar sus versiones. 

 
Aquí te dejamos uno ejemplo del archivo ```my_env.yml```:
```yaml
name: my_environment
channels: 
  - anaconda
  - conda-forge
dependencies: 
  - keras 
  - tensorflow
```

Luego de crear esta configuracion de nuestras librerias, vamos a proceder a crear nuestro entorno.

##### Creacion del Entorno
Ahora, ya en nuestro servidor remoto, vamos a seguir los siguientes pasos:

1. Cargar el modulo de conda :```module load conda```.

1. Crear el entorno: `conda env create -f my_env.yml`. 
Considere aquí que el archivo a crear debe tener el nombre de mi configuracion ya creada en __YAML__.

1. Ya creado, tendremos los siguientes comandos para activar o desactivar nuestro entorno: `conda activate my_environment` o `conda deactivate`. Considere que el entorno tomara el nombre que se haya especificado en el archivo _.yml_ en la seccion _name_.

>[!NOTE]
> Si desea eliminar el entorno, utilice
> `conda env remove --name my_environment`

###### Entorno Basico

Si deseas crear un entorno basico, sin el uso necesario de un archivo _.yml_ puedes crearlo haciendo :
```conda create --name 'my_env' python``` o ```conda create -n 'my_env' python = 3.9```

Este comando te ayudara a crear un entorno rapido y basico donde podrás agregarle las librerias que necesites a medida vayas creando tu proecto.

Espero te haya servido :D! 