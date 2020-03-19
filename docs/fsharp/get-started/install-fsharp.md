---
title: Instalación de F#
description: Obtenga información sobre cómo instalar F de varias maneras diferentes.
ms.date: 12/20/2019
ms.openlocfilehash: 302e04f7cf3271516dff88d9d5f18f620b6ede80
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "79401098"
---
# <a name="install-f"></a>Instalar F\#

Puede instalar F de varias maneras, dependiendo de su entorno.

## <a name="install-f-with-visual-studio"></a>Instalar F con Visual Studio

1. Si va a descargar [Visual Studio](https://visualstudio.microsoft.com/downloads/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link&utm_content=download+vs2019) por primera vez, primero instalará Visual Studio Installer. Instale la edición adecuada de Visual Studio desde el instalador.

   Si ya tiene visual de Visual Studio instalado, elija **Modificar** junto a la edición a la que desea agregar F.

2. En la página Cargas de trabajo, seleccione la carga de **trabajo de desarrollo ASP.NET y web,** que incluye compatibilidad con F y .NET Core para proyectos de ASP.NET Core.

3. Elija **Modificar** en la esquina inferior derecha para instalar todo lo que ha seleccionado.

   A continuación, puede abrir Visual Studio con F, elija **Iniciar** en el instalador de Visual Studio.

## <a name="install-f-with-visual-studio-code"></a>Instalar F con Visual Studio Code

1. Asegúrese de [que](https://git-scm.com/download) git está instalado y disponible en su PATH. Puede comprobar que está instalado correctamente `git --version` introduciendo en un símbolo del sistema y pulsando **Intro**.

2. Instale el SDK de [.NET Core](https://dotnet.microsoft.com/download) y Visual Studio [Code.](https://code.visualstudio.com)

3. Seleccione el icono Extensiones y busque "Ionide":

   El único complemento necesario para la compatibilidad con F en Visual Studio Code es [Ionide-fsharp](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-fsharp). Sin embargo, también puede instalar [Ionide-FAKE](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-FAKE) para obtener soporte [FAKE](https://fake.build/) e [Ionide-Paket](https://marketplace.visualstudio.com/items?itemName=Ionide.Ionide-Paket) para obtener soporte [de Paket.](https://fsprojects.github.io/Paket/) FAKE y Paket son herramientas adicionales de la comunidad de F para crear proyectos y administrar dependencias, respectivamente.

## <a name="install-f-with-visual-studio-for-mac"></a>Instalar F con Visual Studio para Mac

F se instala de forma predeterminada en [Visual Studio para Mac,](https://visualstudio.microsoft.com/vs/mac/?utm_medium=microsoft&utm_source=docs.microsoft.com&utm_campaign=inline+link)independientemente de la configuración que elija.

Una vez completada la instalación, elija **Iniciar Visual Studio**. También puede abrir Visual Studio a través de Finder en macOS.

## <a name="install-f-on-a-build-server"></a>Instalar F en un servidor de compilación

Si usa .NET Core o .NET Framework a través del SDK de .NET, solo tiene que instalar el SDK de .NET en el servidor de compilación. Tiene todo lo que necesitas.

Si usa .NET Framework y **no** usa el SDK de .NET, deberá instalar la [SKU](https://visualstudio.microsoft.com/thank-you-downloading-visual-studio/?sku=BuildTools&rel=16) de Visual Studio Build Tools en Windows Server. En el instalador, seleccione Herramientas de compilación de escritorio de **.NET**y, a continuación, seleccione el componente **del compilador** de F en el lado derecho del menú del instalador.
