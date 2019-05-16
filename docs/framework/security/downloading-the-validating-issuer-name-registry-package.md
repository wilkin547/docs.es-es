---
title: Descargar el paquete de validación del Registro de nombres de emisores
ms.date: 10/10/2018
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
ms.openlocfilehash: 5684844f1db33b075df099b3026d9d0c1061199f
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65631845"
---
# <a name="download-the-validating-issuer-name-registry-package"></a>Descargue el paquete de registro de nombres de validación del emisor

En este tema se explica cómo descargar y usar el Registro de nombres del emisor que valida (VINR) en el proyecto.

El VINR está disponible como un paquete NuGet, que agrega las referencias y los ensamblados necesarios al proyecto. Si aún no tiene NuGet instalado, vaya a [nuget.org](https://nuget.org) para instalarlo. Puede ver el historial de control de versiones para la extensión si visita su página en NuGet: [Validar el registro de nombre de emisor en NuGet de Microsoft](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/)

## <a name="use-the-package-manager-gui"></a>Usar la GUI del Administrador de paquetes

1. En Visual Studio, haga clic con el botón derecho en el proyecto en el **Explorador de soluciones** y, después, seleccione **Administrar paquetes NuGet**.

2. En la ventana **Administrar paquetes NuGet**, haga clic en el cuadro de búsqueda, escriba `ValidatingIssuerNameRegistry` y presione **Entrar**.

3. En el panel de resultados, haga clic en el botón **Instalar** del primer resultado.

4. El paquete comenzará la descarga. Antes de agregarlo al proyecto, aparecerá el diálogo de aceptación de licencia. Si acepta los términos de licencia, haga clic en **Acepto**.

5. Los últimos ensamblados VINR se descargarán y agregarán al proyecto.

## <a name="use-the-package-manager-console"></a>Use la consola de administrador de paquetes

1. En Visual Studio, haga clic en **herramientas** > **Administrador de paquetes de NuGet** > **Package Manager Console**.

2. Aparece la **Consola del Administrador de paquetes**. Escriba el texto siguiente y presione **Entrar**:

    ```powershell
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry
    ```

3. Los últimos ensamblados VINR se descargarán y agregarán al proyecto.
