---
title: Descargar el paquete del controlador de token web de JSON
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
caps.latest.revision: "3"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.openlocfilehash: d3821ff1da945df7c6e07e5baf69730173eacc87
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="downloading-the-json-web-token-handler-package"></a>Descargar el paquete del controlador de token web de JSON
En este tema se explica cómo descargar y usar el controlador de token web JSON en el proyecto.  
  
## <a name="downloading-the-json-web-token-handler"></a>Descargar el controlador de token web de JSON  
 La extensión del controlador de token web JSON está disponible como paquete NuGet, que agrega los ensamblados y referencias necesarios al proyecto. Si aún no tiene NuGet instalado, vaya a [nuget.org](http://nuget.org) para instalarlo. Puede ver el historial de creación de versiones para la extensión si visita su página en NuGet: [Controlador de token web JSON en NuGet](http://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/).  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-gui"></a>Descargar el controlador de token web JSON mediante la GUI del Administrador de paquetes  
  
1.  En Visual Studio, haga clic con el botón derecho en el proyecto en el **Explorador de soluciones** y, después, seleccione **Administrar paquetes NuGet**.  
  
2.  En la ventana **Administrar paquetes NuGet**, haga clic en el cuadro de búsqueda, escriba `JWT Token Handler` y presione **Entrar**.  
  
3.  En el panel de resultados, haga clic en el botón **Instalar** del primer resultado.  
  
4.  El paquete comenzará la descarga. Antes de agregarlo al proyecto, aparecerá el diálogo de aceptación de licencia. Si acepta los términos de licencia, haga clic en **Acepto**.  
  
5.  Los últimos ensamblados de controlador de token web JSON se descargarán y agregarán al proyecto.  
  
#### <a name="downloading-the-json-web-token-handler-by-using-the-package-manager-console"></a>Descargar el controlador de token web JSON mediante la Consola del Administrador de paquetes  
  
1.  En Visual Studio, haga clic en **Herramientas**, **Administrador de paquetes de biblioteca** y, después, **Consola del Administrador de paquetes**.  
  
2.  Aparece la **Consola del Administrador de paquetes**. Escriba el texto siguiente y presione **Entrar**:  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.Jwt  
    ```  
  
3.  Los últimos ensamblados de controlador de token web JSON se descargarán y agregarán al proyecto.
