---
title: Descargar el paquete del controlador de token web de JSON
ms.date: 10/10/2018
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
ms.openlocfilehash: 8f878d23afd76488de7da03f16f72cbfa43c17d7
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61792761"
---
# <a name="download-the-json-web-token-handler-package"></a>Descargue el paquete de controladores de Token Web JSON

En este tema se explica cómo descargar y usar el controlador de token web JSON en el proyecto.

La extensión del controlador de token web JSON está disponible como paquete NuGet, que agrega los ensamblados y referencias necesarios al proyecto. Si aún no tiene NuGet instalado, vaya a [nuget.org](https://nuget.org) para instalarlo. Puede ver el historial de control de versiones para la extensión si visita su página en NuGet: [Controlador de Token Web JSON en NuGet](https://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)

## <a name="use-the-package-manager-gui"></a>Usar la GUI del Administrador de paquetes

1. En Visual Studio, haga clic con el botón derecho en el proyecto en el **Explorador de soluciones** y, después, seleccione **Administrar paquetes NuGet**.

2. En la ventana **Administrar paquetes NuGet**, haga clic en el cuadro de búsqueda, escriba `JWT Token Handler` y presione **Entrar**.

3. En el panel de resultados, haga clic en el botón **Instalar** del primer resultado.

4. El paquete comenzará la descarga. Antes de agregarlo al proyecto, aparecerá el diálogo de aceptación de licencia. Si acepta los términos de licencia, haga clic en **Acepto**.

5. Los últimos ensamblados de controlador de token web JSON se descargarán y agregarán al proyecto.

## <a name="use-the-package-manager-console"></a>Use la consola de administrador de paquetes

1. En Visual Studio, haga clic en **herramientas** > **Administrador de paquetes de NuGet** > **Package Manager Console**.

2. Aparece la **Consola del Administrador de paquetes**. Escriba el texto siguiente y presione **Entrar**:

    ```powershell
    Install-Package System.IdentityModel.Tokens.Jwt
    ```

3. Los últimos ensamblados de controlador de token web JSON se descargarán y agregarán al proyecto.