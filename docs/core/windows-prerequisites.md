---
title: Requisitos previos para .NET Core en Windows
description: Obtenga información sobre qué dependencias necesita en la máquina con Windows para desarrollar y ejecutar aplicaciones .NET Core.
f1_keywords:
- NETSDK1045
ms.custom: updateeachvsrelease
ms.date: 09/20/2019
ms.openlocfilehash: 6885f6c853efb0dcb2cb64b83f07e12b1dc2e3cf
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72771953"
---
# <a name="prerequisites-for-net-core-on-windows"></a>Requisitos previos para .NET Core en Windows

En este artículo se muestran las versiones compatibles del sistema operativo para ejecutar aplicaciones .NET Core en Windows. Las versiones del sistema operativo y las dependencias admitidas que aparecen a continuación se aplican a las tres formas de desarrollo de aplicaciones de .NET Core en Windows:

* [Línea de comandos](./tutorials/using-with-xplat-cli.md)
* [Visual Studio](https://www.visualstudio.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=button+cta&utm_content=download+vs2019)
* [Visual Studio Code](https://code.visualstudio.com/)

Además, si desarrolla en Windows con Visual Studio, en la sección [Requisitos previos para desarrollar aplicaciones de .NET Core con Visual Studio](#prerequisites-to-develop-net-core-apps-with-visual-studio), puede encontrar más información sobre las versiones mínimas compatibles con el desarrollo de .NET Core.

## <a name="net-core-supported-operating-systems"></a>Sistemas operativos admitidos por .NET Core

Los artículos siguientes incluyen una lista completa de sistemas operativos de .NET Core compatibles por versión:

* [.NET Core 3.0](https://github.com/dotnet/core/blob/master/release-notes/3.0/3.0-supported-os.md)
* [.NET Core 2.2](https://github.com/dotnet/core/blob/master/release-notes/2.2/2.2-supported-os.md)
* [.NET Core 2.1](https://github.com/dotnet/core/blob/master/release-notes/2.1/2.1-supported-os.md)

Para vínculos de descarga y más información, vaya a [Descargas de .NET](https://dotnet.microsoft.com/download) para descargar la versión más reciente o al [archivo de descargas de .NET](https://dotnet.microsoft.com/download/archives#dotnet-core) para versiones anteriores.

## <a name="net-core-dependencies"></a>Dependencias de .NET Core

[Microsoft Visual C++ 2015 Redistributable Update 3](https://www.microsoft.com/download/details.aspx?id=52685) debe instalarse de forma manual en los siguientes casos:

* A l instalar .NET Core con el [script de instalación](./tools/dotnet-install-script.md).
* Al implementar una aplicación de .NET Core independiente.
* Al compilar el producto desde el origen.
* Al instalar .NET Core a través de un archivo *.zip*. Esto puede incluir servidores de compilación, integración continua o implementación continua.

> [!NOTE]
> **Para Windows 8.1 y versiones anteriores o Windows Server 2012 R2 y versiones anteriores:**
>
> Asegúrese de que la instalación de Windows está actualizada e incluye la revisión [KB2999226](https://support.microsoft.com/help/2999226/update-for-universal-c-runtime-in-windows), que se puede instalar mediante Windows Update. Si no tiene instalada esta actualización, verá un error similar al siguiente al iniciar una aplicación de .NET Core: `The program can't start because api-ms-win-crt-runtime-l1-1-0.dll is missing from your computer. Try reinstalling the program to fix this problem.`.
>
> **Para Windows 7 o Windows Server 2008 R2:**
>
> Además de KB2999226, asegúrese de que también tiene instalada [KB2533623](https://support.microsoft.com/help/2533623/microsoft-security-advisory-insecure-library-loading-could-allow-remot). Si no tiene instalada esta actualización, verá un error similar al siguiente al iniciar una aplicación de .NET Core: `The library hostfxr.dll was found, but loading it from C:\<path_to_app>\hostfxr.dll failed`.

## <a name="prerequisites-to-develop-net-core-apps-with-visual-studio"></a>Requisitos previos para desarrollar aplicaciones de .NET Core con Visual Studio

Aunque puede usar cualquier editor para desarrollar aplicaciones de .NET Core con el SDK de .NET Core, Visual Studio 2017 y las versiones posteriores proporcionan un entorno de desarrollo integrado para las aplicaciones de .NET Core en Windows.

<a name="vs-mapping"></a>

Cada versión de .NET Core requiere una versión mínima de Visual Studio. Para comprobar la versión de Visual Studio, haga lo siguiente:

* En el menú **Ayuda**, elija **Acerca de Microsoft Visual Studio**.
* En el cuadro de diálogo **Acerca de Microsoft Visual Studio**, compruebe el número de versión.

En la tabla siguiente se muestra la versión mínima de cada SDK:

| Versión del SDK de .NET Core | Versión de Visual Studio                      |
| --------------------- | ------------------------------------------ |
| 3.0                   | Visual Studio 2019, versión 16.3 o posterior. |
| 2.2                   | Visual Studio 2017, versión 15.9 o posterior. |
| 2.1                   | Visual Studio 2017, versión 15.7 o posterior. |
| 1.x                   | Visual Studio 2017, versión 15.0 o posterior. |

<!-- markdownlint-disable MD025 -->

# <a name="net-core-30tabnetcore30"></a>[.NET Core 3.0](#tab/netcore30)

Para desarrollar aplicaciones de .NET Core en Visual Studio 2019 con el SDK de .NET Core 3.0:

* [Descargue e instale Visual Studio 2019 versión 16.3 o una versión superior](/visualstudio/install/install-visual-studio) y seleccione una de las siguientes cargas de trabajo que incluye el SDK de .NET Core según el tipo de aplicación que esté desarrollando:

  * La carga de trabajo **Desarrollo multiplataforma de .NET Core** en la sección **Otros conjuntos de herramientas**.
  * La carga de trabajo **Desarrollo de ASP.NET y web** en la sección **Web y nube**.
  * La carga de trabajo **Desarrollo de escritorio de .NET** en la sección **Windows**.

En la siguiente imagen se muestra la carga de trabajo **Desarrollo multiplataforma de .NET Core** seleccionada en la interfaz de usuario de Visual Studio:

![Captura de pantalla de la instalación de Visual Studio 2019 con la carga de trabajo “Desarrollo multiplataforma de .NET Core” seleccionada](./media/windows-prerequisites/vs-2019-workloads.jpg)

La versión 16.3 de Visual Studio 2019 usa el SDK de .NET Core 3.0 de manera predeterminada una vez que se instala cualquiera de estas cargas de trabajo.

Si quiere que sus proyectos existentes usen el runtime de .NET Core más reciente, redestine cada uno de los proyectos de .NET Core existentes a .NET Core 3.0 según las instrucciones siguientes:

* En el menú **Proyecto** , elija **Propiedades**.
* En el menú de selección **Plataforma de destino**, establezca el valor en **.NET Core 3.0**.

![Captura de pantalla de la propiedad de proyecto de aplicación de Visual Studio 2019 con el elemento de menú Plataforma de destino “.NET Core 3.0” seleccionado](./media/windows-prerequisites/target-dotnet-core-3-0.jpg)

Una vez que Visual Studio está configurado con el SDK de .NET Core 3.0, puede realizar las siguientes acciones:

* Abrir, compilar y ejecutar proyectos de .NET Core 1.x y 2.x existentes.
* Redestinar proyectos de .NET Core 1.x y 2.x a .NET Core 3.0, compilarlos y ejecutarlos.
* Crear proyectos de .NET Core 3.0.

# <a name="net-core-2xtabnetcore2x"></a>[.NET Core 2.x](#tab/netcore2x)

Para desarrollar aplicaciones .NET Core en Visual Studio 2017 con el SDK de .NET Core 2.2:

* [Descargue e instale Visual Studio 2019 versión 16.3 o una versión superior](/visualstudio/install/install-visual-studio) con la carga de trabajo **Desarrollo multiplataforma de .NET Core** (en la sección **Otros conjuntos de herramientas**) seleccionada.
* [Descargue e instale Visual Studio 2017 versión 15.9.0 o una versión superior](/visualstudio/install/install-visual-studio) con la carga de trabajo **Desarrollo multiplataforma de .NET Core** (en la sección **Otros conjuntos de herramientas**) seleccionada.

![Captura de pantalla de la instalación de Visual Studio 2017 con la carga de trabajo "Desarrollo multiplataforma de .NET Core" seleccionada](./media/windows-prerequisites/vs-2017-workloads.jpg)

Una vez instalado el conjunto de herramientas **Desarrollo multiplataforma de .NET Core**, Visual Studio habitualmente instala una versión anterior del SDK de .NET Core.
Por ejemplo, la versión 15.9 de Visual Studio 2017 usa el SDK de .NET Core 2.1 de manera predeterminada una vez que se instala la carga de trabajo.

Para actualizar Visual Studio para que use el SDK de .NET Core 2.2:

 1. Instale el [SDK de .NET Core 2.2](https://dotnet.microsoft.com/download).

 1. Si quiere que el proyecto use el runtime de .NET Core más reciente, redestine cada uno de los proyectos de .NET Core nuevos o existentes a .NET Core 2.2 según las instrucciones siguientes:

    * En el menú **Proyecto** , elija **Propiedades**.
    * En el menú de selección **Plataforma de destino**, establezca el valor en **.NET Core 2.2**.

![Captura de pantalla de la propiedad de proyecto de aplicación de Visual Studio 2017 con el elemento de menú Plataforma de destino ".NET Core 2.2" seleccionado](./media/windows-prerequisites/targeting-dotnet-core.jpg)

Una vez que Visual Studio está configurado con el SDK de .NET Core 2.2, puede realizar las siguientes acciones:

* Abrir, compilar y ejecutar proyectos de .NET Core 1.x y 2.x existentes.
* Redestinar proyectos de .NET Core 1.x y 2.x a .NET Core 2.2, compilarlos y ejecutarlos.
* Crear proyectos de .NET Core 2.2.

---
