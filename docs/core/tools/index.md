---
title: "Herramientas de la interfaz de línea de comandos (CLI) de .NET Core"
description: "Información general sobre qué es la interfaz de línea de comandos (CLI) y sus características principales"
keywords: CLI, herramientas de la CLI, .NET, .NET Core
author: blackdwarf
ms.author: mairaw
manager: wpickett
ms.date: 10/06/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: b70e9ac0-c8be-49f7-9332-95ab93e0e7bc
translationtype: Human Translation
ms.sourcegitcommit: b20713600d7c3ddc31be5885733a1e8910ede8c6
ms.openlocfilehash: 3a3326f96cf69d0ac466e52107597d80c2790b62

---

# <a name="net-core-commandline-interface-tools"></a>Herramientas de la interfaz de la línea de comandos de .NET Core

La interfaz de la línea de comandos (CLI) de .NET Core es una nueva cadena de herramientas fundamental multiplataforma para el desarrollo de aplicaciones .NET Core. Es "fundamental" porque es la capa primaria sobre la que se pueden crear otras herramientas de nivel superior, como entornos de desarrollo integrados (IDE), editores y orquestadores de compilación. 

También es multiplataforma de forma predeterminada y tiene la misma área de superficie en cada una de las plataformas admitidas. Esto significa que cuando aprenda a usar las herramientas, puede usarlas de la misma forma desde cualquiera de las plataformas compatibles. 

## <a name="installation"></a>Instalación
Del mismo modo que ocurre con todas las herramientas, lo primero que debe hacer es instalar las herramientas en su máquina. En función del escenario, puede usar a los instaladores nativos para instalar la CLI o el script de shell de instalación.

Los instaladores nativos están pensados principalmente para las máquinas de los desarrolladores. La CLI se distribuye mediante el mecanismo de instalación nativo de cada plataforma compatible, por ejemplo, los paquetes DEB en Ubuntu o los paquetes MSI en Windows. Estos instaladores instalarán y configurarán el entorno según sea necesario para que el usuario utilice la CLI inmediatamente después de la instalación. Sin embargo, también se necesitan privilegios administrativos en la máquina. Puede consultar las instrucciones de instalación en la [página de introducción a .NET Core](https://aka.ms/dotnetcoregs).

Por otro lado, los scripts de instalación no requieren privilegios administrativos. Sin embargo, tampoco instalan ningún requisito previo en la máquina; debe instalarlos todos manualmente. Los scripts están diseñados principalmente para configurar servidores de compilación o cuando se desea instalar las herramientas sin privilegios administrativos (tenga en cuenta la advertencia anterior sobre los requisitos previos). Puede encontrar más información en el [tema de referencia sobre los scripts de instalación](dotnet-install-script.md). Si está interesado en cómo configurar la CLI en el servidor de compilación de integración continua (CI), puede echar un vistazo al tema [CLI con servidores de CI](using-ci-with-cli.md). 

De forma predeterminada, la CLI se instalará en paralelo. Esto significa que pueden coexistir varias versiones de las herramientas de la CLI en un momento dado en una sola máquina. En la sección sobre los [controladores](#driver) se explica con mayor detalle cómo usar la versión correcta. 

### <a name="what-commands-come-in-the-box"></a>¿Qué comandos se incluyen en el cuadro?
De forma predeterminada, se instalan los siguientes comandos:

* [new](dotnet-new.md)
* [restore](dotnet-restore.md)
* [run](dotnet-run.md)
* [build](dotnet-build.md)
* [test](dotnet-test.md)
* [publish](dotnet-publish.md)
* [pack](dotnet-pack.md)

También hay una manera de importar más comandos en un modelo de herramientas por proyecto y de agregar sus propios comandos. Esto se explica con más detalle en la [sección sobre extensibilidad](#extensibility). 

## <a name="working-with-the-cli"></a>La CLI

Antes de entrar en más detalles, vamos a ver cómo es trabajar con la CLI desde una vista a 10 000 pies. En el ejemplo siguiente se usan varios comandos de la instalación estándar de la CLI para inicializar una nueva aplicación de consola sencilla, restaurar las dependencias, compilar la aplicación y luego ejecutarla. 

```console
dotnet new
dotnet restore
dotnet build --output /stuff
dotnet /stuff/new.dll
```

Como puede ver en el ejemplo anterior, hay un patrón en la forma de usar las herramientas de la CLI. Dentro de ese patrón, podemos identificar tres elementos principales de cada comando:

1. [El controlador ("dotnet")](#driver)
2. [El comando o "verbo"](#the-verb)
3. [Los argumentos de comandos](#the-arguments)

### <a name="driver"></a>Controlador
El controlador se denomina [dotnet](dotnet.md). Es la primera parte de lo que se invoca. El controlador tiene dos responsabilidades:

1. Ejecutar las aplicaciones portátiles
2. Ejecuta el verbo

Lo que haga depende de lo especificado en la línea de comandos. En el primer caso, especificaría una DLL de aplicación portátil que `dotnet` se ejecutaría de forma parecida a esta: `dotnet /path/to/your.dll`. 

En el segundo caso, el controlador intenta invocar el comando especificado. Esto inicia el proceso de ejecución del comando de la CLI. En primer lugar, el controlador determina la versión de las herramientas que quiere. Puede especificar la versión en el archivo [global.json](global-json.md) mediante la propiedad `version`. Si no está disponible, el controlador busca la versión más reciente de las herramientas que se instalará en el disco y usará esa versión. Una vez determinada la versión, se ejecuta el comando. 

### <a name="the-verb"></a>El "verbo"
El verbo es simplemente un comando que realiza una acción. `dotnet build` compila el código. `dotnet publish` publica el código. El verbo se implementa como una aplicación de consola que se nombra según la convención: `dotnet-{verb}`. Toda la lógica se implementa en la aplicación de consola que representa el verbo. 

### <a name="the-arguments"></a>Los argumentos
Los argumentos que se pasan en la línea de comandos son los argumentos para el verbo/comando real que se invoca. Por ejemplo, cuando escribe `dotnet publish --output publishedapp`, el argumento `--output` se pasa al comando `publish`. 

## <a name="types-of-application-portability"></a>Tipos de portabilidad de aplicaciones
La CLI permite que las aplicaciones sean portátiles de dos maneras principalmente:

1. Aplicaciones completamente portátiles que se pueden ejecutar en cualquier parte donde esté instalado .NET Core
2. Implementaciones autocontenidas

Puede aprender más sobre ambas en el tema [Implementación de aplicaciones .NET Core](../deploying/index.md). 

## <a name="migration-from-dnx"></a>Migración desde DNX
Si ha usado DNX en .NET Core 1.0 RC1, puede que se esté preguntando qué ha pasado con él y cómo se relacionan estas nuevas herramientas con las herramientas DNX. En pocas palabras, las herramientas DNX se han reemplazado por las herramientas de la CLI de .NET Core. Si tiene proyectos existentes o simplemente se pregunta cómo se asignan los comandos, puede consultar el tema sobre la [migración de DNX a la CLI](../migrating-from-dnx.md) para más información. 

## <a name="extensibility"></a>Extensibilidad
Por supuesto, no todas las herramientas que puede usar en el flujo de trabajo van a ser parte de las herramientas de la CLI de .NET Core. Sin embargo, esta CLI tiene un modelo de extensibilidad que le permite especificar herramientas adicionales para sus proyectos. Puede encontrar más información en el tema [Modelo de extensibilidad de la CLI de .NET Core](extensibility.md).

## <a name="summary"></a>Resumen
Esta ha sido una corta introducción a las características más importantes de la CLI. Puede encontrar más información en la referencia y los temas conceptuales en este sitio. También hay otros recursos que puede usar:
* [dotnet/CLI,](https://github.com/dotnet/cli/) repositorio de GitHub
* [Instrucciones de inicio](https://aka.ms/dotnetcoregs/)



<!--HONumber=Nov16_HO1-->


