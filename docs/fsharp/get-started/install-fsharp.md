---
title: InstalarF#
description: Obtenga información sobre cómo instalar F# basándose en su entorno.
ms.date: 08/28/2018
ms.openlocfilehash: 873d3021ba884ec81992469e5d0f3b7c18b1e0f4
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56975256"
---
# <a name="install-f"></a>Instalar F\#

Puede instalar F# de varias maneras, dependiendo de su entorno.

## <a name="install-f-with-visual-studio"></a>Instalar F# con Visual Studio

Si está descargando [Visual Studio](https://visualstudio.microsoft.com/) por primera vez, instalará el instalador de Visual Studio. Instale el adecuado SKU de Visual Studio desde el instalador. Si ya tiene instalado, haga clic en **modificar**.

A continuación verá una lista de las cargas de trabajo. Seleccione **ASP.NET y desarrollo web** que instalará F# soporte de soporte técnico y .NET Core para proyectos de ASP.NET Core.

A continuación, haga clic en **modificar** en el lado inferior derecho.  Así instalará todo lo que ha seleccionado. A continuación, puede abrir Visual Studio 2017 con F# compatibilidad de idioma, haga clic en **iniciar**.

## <a name="install-f-with-visual-studio-for-mac"></a>Instalar F# con Visual Studio para Mac

F#se instala de forma predeterminada en [Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/), con independencia de la configuración elija.

Una vez finalizada la instalación, elija "Iniciar Visual Studio". También puede iniciar a través de Finder de macOS.

## <a name="install-f-with-visual-studio-code"></a>Instalar F# con Visual Studio Code

Debe tener [git instalado](https://git-scm.com/download) y está disponible en la ruta de acceso para hacer uso de plantillas de proyecto. Puede comprobar que está instalado correctamente escribiendo `git --version` en un símbolo del sistema y presione **ENTRAR**.

### <a name="macostabmacos"></a>[macOS](#tab/macos)

[Mono](https://www.mono-project.com) se usa para [ F# interactivo](../tutorials/fsharp-interactive/index.md) admite. La manera más fácil para instalar Mono en macOS es a través de Homebrew. Basta con escribir lo siguiente en el terminal:

```console
brew install mono
```

Instale también la [SDK de .NET Core](https://www.microsoft.com/net/download).

### <a name="linuxtablinux"></a>[Linux](#tab/linux)

[Mono](https://www.mono-project.com) se usa para [ F# interactivo](../tutorials/fsharp-interactive/index.md) admite. Si se encuentra en Debian o Ubuntu, puede utilizar lo siguiente:

```console
sudo apt-get update
sudo apt-get install mono-complete fsharp
```

Instale también la [SDK de .NET Core](https://www.microsoft.com/net/download).

### <a name="windowstabwindows"></a>[Windows](#tab/windows)

Instalar [Visual Studio con F# admite](#install-f-with-visual-studio). Esto instala todos los componentes necesarios para escribir, compilar y ejecutar F# código.

Instale también la [SDK de .NET Core](https://www.microsoft.com/net/download/).

---

A continuación, necesitará [Visual Studio Code](https://code.visualstudio.com) instalado.

A continuación, haga clic en el icono de extensiones y busque "Ionide":

El complemento solo necesario para F# compatibilidad en Visual Studio Code es [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp). Sin embargo, también puede instalar [Ionide FALSIFICACIÓN](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) obtener [IMITAR](https://fsharp.github.io/FAKE/) admite y [Ionide Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) para obtener [Paket](https://fsprojects.github.io/Paket/) admite. FALSIFICAR y Paket son adicionales F# herramientas de la Comunidad para crear proyectos y administrar las dependencias, respectivamente.
