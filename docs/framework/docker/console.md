---
title: "Ejecución de aplicaciones de consola en Docker"
description: "Aprenda a ejecutar una aplicación de consola existente de .NET Framework en un contenedor de Docker de Windows."
author: spboyer
keywords: .NET, contenedor, consola, aplicaciones
ms.date: 09/28/2016
ms.topic: article
ms.prod: .net-framework
ms.technology: vs-ide-deployment
ms.devlang: dotnet
ms.assetid: 85cca1d5-c9a4-4eb2-93e6-4f878de07fd7
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 2fdce1e131eaa0d6952b2910f73105f097487711
ms.contentlocale: es-es
ms.lasthandoff: 08/11/2017

---

# <a name="running-console-applications-in-windows-containers"></a>Ejecución de aplicaciones de consola en contenedores de Windows

Las aplicaciones de consola se usan para muchos fines, que abarcan desde la consulta simple de un estado a tareas de procesamiento de imágenes de documentos de ejecución prolongada. En cualquier caso, la posibilidad de iniciar y escalar estas aplicaciones se enfrenta a limitaciones de adquisiciones de hardware, tiempos de inicio o ejecución de varias instancias.

La migración de las aplicaciones de consola a contenedores de Docker y Windows Server permite iniciar estas aplicaciones desde un estado limpio, lo que facilita su funcionamiento y cierre sin problemas. En este tema se explican los pasos necesarios para migrar una aplicación de consola a un contenedor basado en Windows y para iniciarla mediante un script de PowerShell.

La aplicación de consola de ejemplo es un ejemplo sencillo que toma un argumento, una pregunta en este caso, y devuelve una respuesta aleatoria. Podría tomar un `customer_id` y procesar sus impuestos o crear una miniatura para un argumento `image_url`.

Además de la respuesta, se ha agregado `Environment.MachineName` a ella para mostrar la diferencia entre la ejecución local de la aplicación y en un contenedor de Windows. Cuando la aplicación se ejecuta localmente, se debería devolver el nombre del equipo local, mientras que cuando se ejecuta en un contenedor de Windows, se devuelve el identificador de sesión del contenedor.

El [ejemplo completo](https://github.com/dotnet/docs/tree/master/samples/framework/docker/ConsoleRandomAnswerGenerator) está disponible en el repositorio dotnet/docs de GitHub. Para obtener instrucciones de descarga, vea [Ejemplos y tutoriales](../../samples-and-tutorials/index.md#viewing-and-downloading-samples).

Antes de empezar a trabajar en la migración de la aplicación a un contenedor, debe estar familiarizado con algunos términos de Docker.

> Una *imagen de Docker* es una plantilla de solo lectura que define el entorno de un contenedor en ejecución, incluidos el sistema operativo (SO), los componentes del sistema y las aplicaciones.

Una característica importante de las imágenes de Docker es que se forman a partir de una imagen base. Cada nueva imagen agrega un pequeño conjunto de características a una imagen existente. 

> Un *contenedor de Docker* es una instancia en ejecución de una imagen. 

Una aplicación se escala al ejecutar la misma imagen en muchos contenedores.
Conceptualmente, esto es similar a la ejecución de la misma aplicación en varios hosts.

Puede obtener más información sobre la arquitectura de Docker si lee [Docker Overview (Introducción a Docker)](https://docs.docker.com/engine/understanding-docker/) en el sitio de Docker. 

La migración de la aplicación de consola se realiza en unos pocos pasos.

1. [Compilar la aplicación](#building-the-application)
1. [Creación de un Dockerfile para la imagen](#creating-the-dockerfile)
1. [Proceso para compilar y ejecutar el contenedor de Docker](#creating-the-image)

## <a name="prerequisites"></a>Requisitos previos
Los contenedores de Windows son compatibles con [Actualización de aniversario de Windows 10](https://www.microsoft.com/en-us/software-download/windows10/) o [Windows Server 2016](https://www.microsoft.com/en-us/cloud-platform/windows-server).

> [!NOTE]
>Si usa Windows Server 2016, debe habilitar los contenedores de forma manual, ya que el instalador de Docker para Windows no habilitará la característica. Asegúrese de que todas las actualizaciones del sistema operativo se hayan ejecutado y luego siga las instrucciones del artículo [Implementación de host de contenedor](https://msdn.microsoft.com/virtualization/windowscontainers/deployment/deployment) para instalar los contenedores y las características de Docker.

Para admitir los contenedores de Windows, debe tener Docker para Windows, versión 1.12 Beta 26 o superior. De forma predeterminada, Docker habilita los contenedores basados en Linux. Cambie a los contenedores de Windows al hacer clic con el botón derecho en el icono de Docker de la bandeja del sistema y seleccionar la opción para **cambiar a contenedores de Windows**. Docker ejecutará el proceso de cambio. Es posible que sea necesario reiniciar.

![Contenedores de Windows](./media/console/SwitchContainer.png)

## <a name="building-the-application"></a>Compilación de la aplicación
Normalmente las aplicaciones de consola se distribuyen a través de un instalador, un FTP o una implementación de recurso compartido de archivos. Al implementar en un contenedor, los activos tienen que compilarse y colocarse en una ubicación que se pueda usar una vez creada la imagen de Docker.

En *build.ps1*, el script usa [MSBuild](https://msdn.microsoft.com/library/dd393574.aspx) para compilar la aplicación a fin de completar la tarea de creación de los activos. Algunos parámetros se pasan a MSBuild para finalizar los activos necesarios. El nombre del archivo del proyecto o la solución que se va a compilar, la ubicación de la salida y, por último, la configuración (lanzamiento o depuración).

En la llamada a `Invoke-MSBuild`, `OutputPath` se establece en **publish** y `Configuration` en **Release**. 

```
function Invoke-MSBuild ([string]$MSBuildPath, [string]$MSBuildParameters) {
    Invoke-Expression "$MSBuildPath $MSBuildParameters"
}

Invoke-MSBuild -MSBuildPath "MSBuild.exe" -MSBuildParameters ".\ConsoleRandomAnswerGenerator.csproj /p:OutputPath=.\publish /p:Configuration=Release"
```

## <a name="creating-the-dockerfile"></a>Creación del Dockerfile
La imagen base usada para una aplicación de consola de .NET Framework es `microsoft/windowsservercore`, disponible públicamente en [Docker Hub](https://hub.docker.com/r/microsoft/windowsservercore/). La imagen base contiene una instalación mínima de Windows Server 2016, .NET Framework 4.6.2 y sirve como imagen base de sistema operativo para los contenedores de Windows.

```
FROM microsoft/windowsservercore
ADD publish/ /
ENTRYPOINT ConsoleRandomAnswerGenerator.exe
```
La primera línea del Dockerfile designa la imagen base mediante la instrucción [`FROM`](https://docs.docker.com/engine/reference/builder/#/from). Después, el elemento [`ADD`](https://docs.docker.com/engine/reference/builder/#/add) del archivo copia los activos de la aplicación de la carpeta **publish** en la carpeta raíz del contenedor y, por último, el establecimiento de [`ENTRYPOINT`](https://docs.docker.com/engine/reference/builder/#/entrypoint) de la imagen indica que este es el comando o la aplicación que se va a ejecutar cuando se inicie el contenedor. 

## <a name="creating-the-image"></a>Creación de la imagen
Para crear la imagen de Docker, se agrega el código siguiente al script *build.ps1*. Cuando se ejecuta el script, se crea la imagen `console-random-answer-generator` mediante los activos compilados a partir del elemento MSBuild definido en la sección [Compilación de la aplicación](#building-the-application).

```powershell
$ImageName="console-random-answer-generator"

function Invoke-Docker-Build ([string]$ImageName, [string]$ImagePath, [string]$DockerBuildArgs = "") {
    echo "docker build -t $ImageName $ImagePath $DockerBuildArgs"
    Invoke-Expression "docker build -t $ImageName $ImagePath $DockerBuildArgs"
}

Invoke-Docker-Build -ImageName $ImageName -ImagePath "."
```

Ejecute el script mediante el elemento `.\build.ps1` desde el símbolo del sistema de PowerShell.

Una vez completada la compilación, si usa el comando `docker images` desde una línea de comandos o el símbolo del sistema de PowerShell, verá que la imagen está creada y lista para ejecutarse.

```
REPOSITORY                        TAG                 IMAGE ID            CREATED             SIZE
console-random-answer-generator   latest              8f7c807db1b5        8 seconds ago       7.33 GB
```

## <a name="running-the-container"></a>Ejecución del contenedor
Puede iniciar el contenedor desde la línea de comandos mediante los comandos de Docker.

```
docker run console-random-answer-generator "Are you a square container?"
```

El resultado es

```
The answer to your question: 'Are you a square container?' is Concentrate and ask again on (70C3D48F4343)
```

Si ejecuta el comando `docker ps -a` desde PowerShell, puede ver que el contenedor todavía existe.

```
CONTAINER ID        IMAGE                             COMMAND                  CREATED             STATUS                          
70c3d48f4343        console-random-answer-generator   "cmd /S /C ConsoleRan"   2 minutes ago       Exited (0) About a minute ago      
```

La columna STATUS muestra que, "hace aproximadamente un minuto", la aplicación estaba completa y se podía cerrar. Si el comando se ejecuta cien veces, habría cien contenedores estáticos sin ningún trabajo que hacer. En el escenario inicial, la operación ideal era realizar el trabajo y cerrar o limpiar. Para lograr ese flujo de trabajo, agregue la opción `--rm` al comando `docker run`, con lo que se quitará el contenedor en cuanto se reciba la señal `Exited`.

```
docker run --rm console-random-answer-generator "Are you a square container?"
```

Si ejecuta el comando con esta opción y luego examina el resultado del comando `docker ps -a`, observará que el identificador del contenedor (`Environment.MachineName`) no está en la lista.

### <a name="running-the-container-using-powershell"></a>Ejecución del contenedor mediante PowerShell
En los archivos del proyecto de ejemplo también hay un *run.ps1*, que es un ejemplo de cómo usar PowerShell para ejecutar la aplicación que acepta los argumentos.

Para ejecutar, abra PowerShell y use el comando siguiente:

```
.\run.ps1 "Is this easy or what?"
```

## <a name="summary"></a>Resumen
Con solo agregar un Dockerfile y publicar la aplicación, puede colocar en contenedores las aplicaciones de consola de .NET Framework y aprovechar las ventajas que ofrece la ejecución de varias instancias, el inicio y la detención limpios y otras capacidades de Windows Server 2016 sin realizar cambio alguno en el código de las aplicaciones.

