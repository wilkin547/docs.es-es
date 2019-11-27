---
title: Instalación de F#
description: Obtenga información sobre cómo F# instalar en función de su entorno.
ms.date: 09/05/2019
ms.openlocfilehash: 592a4c7763266cee68809fca84f9604d7e96b8f1
ms.sourcegitcommit: 81ad1f09b93f3b3e6706a7f2e4ddf50ef229ea3d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/20/2019
ms.locfileid: "74204872"
---
# <a name="install-f"></a>Instalar F\#

Puede instalar F# de varias maneras, en función de su entorno.

## <a name="install-f-with-visual-studio"></a>Instalación F# con Visual Studio

Si está descargando [Visual Studio](https://visualstudio.microsoft.com/vs/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link) por primera vez, primero instalará el instalador de Visual Studio. Instale la SKU adecuada de Visual Studio desde el instalador. Si ya lo tiene instalado, haga clic en **modificar**.

A continuación verá una lista de cargas de trabajo. Seleccione **ASP.net y desarrollo web** , que instalarán F# compatibilidad con y .net Core para proyectos de ASP.net Core.

A continuación, haga clic en **modificar** en la parte inferior derecha.  Se instalará todo lo que haya seleccionado. Después, puede abrir Visual Studio 2017 con F# compatibilidad con idiomas haciendo clic en **iniciar**.

## <a name="install-f-with-visual-studio-code"></a>Instalación F# con Visual Studio Code

En primer lugar, asegúrese de que tiene [git instalado](https://git-scm.com/download) y disponible en su ruta de acceso. Para comprobar que se ha instalado correctamente, escriba `git --version` en un símbolo del sistema y presione **entrar**.

A continuación, instale el [SDK de .net Core](https://dotnet.microsoft.com/download).

A continuación, necesitará [Visual Studio Code](https://code.visualstudio.com) instalado.

A continuación, haga clic en el icono de extensiones y busque "Ionide":

El único complemento necesario para F# la compatibilidad en Visual Studio Code es [Ionide-FSharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp). Sin embargo, también puede instalar [Ionide-falsificación](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) para obtener compatibilidad [falsa](https://fake.build/) y [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) para obtener soporte técnico de [Paket](https://fsprojects.github.io/Paket/) . FALSAS y Paket son herramientas F# de la comunidad adicionales para la creación de proyectos y la administración de dependencias, respectivamente.

## <a name="install-f-with-visual-studio-for-mac"></a>Instalación F# con Visual Studio para Mac

F#se instala de forma predeterminada en [Visual Studio para Mac](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link), independientemente de la configuración que elija.

Una vez finalizada la instalación, elija "iniciar Visual Studio". También puede iniciarlo a través de Finder en macOS.

## <a name="install-f-on-a-build-server"></a>Instalar F# en un servidor de compilación

Si usa .NET Core o .NET Framework a través del SDK de .NET, solo tiene que instalar el SDK de .NET en el servidor de compilación. Tiene todo lo que necesita.

Si usa .NET Framework y **no** usa el SDK de .net, tendrá que instalar la [SKU de Visual Studio build tools](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) en el servidor de Windows. En el instalador, seleccione **herramientas de compilación de escritorio de .net** y, a continuación, seleccione el  **F# componente del compilador** en el lado derecho del menú del instalador.
