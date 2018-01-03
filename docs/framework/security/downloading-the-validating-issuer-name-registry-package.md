---
title: "Descargar el paquete de validación del Registro de nombres de emisores"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ff8b0014-c5d4-4614-90f0-13fcc0ba777a
caps.latest.revision: "3"
author: wadepickett
ms.author: wpickett
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 9bf6869de939ed7eda7cd3de868e712126f71751
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="downloading-the-validating-issuer-name-registry-package"></a>Descargar el paquete de validación del Registro de nombres de emisores
En este tema se explica cómo descargar y usar el Registro de nombres del emisor que valida (VINR) en el proyecto.  
  
## <a name="downloading-the-validating-issuer-name-registry"></a>Descargar el Registro de nombres del emisor que valida  
 El VINR está disponible como un paquete NuGet, que agrega las referencias y los ensamblados necesarios al proyecto. Si aún no tiene NuGet instalado, vaya a [nuget.org](http://nuget.org) para instalarlo. Puede ver el historial de creación de versiones para la extensión si visita su página en NuGet: [Registro de Microsoft del nombre del emisor que valida en NuGet](https://nuget.org/packages/System.IdentityModel.Tokens.ValidatingIssuerNameRegistry/).  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-gui"></a>Descargar el Registro de nombres del emisor que valida mediante la GUI del Administrador de paquetes  
  
1.  En Visual Studio, haga clic con el botón derecho en el proyecto en el **Explorador de soluciones** y, después, seleccione **Administrar paquetes NuGet**.  
  
2.  En la ventana **Administrar paquetes NuGet**, haga clic en el cuadro de búsqueda, escriba `ValidatingIssuerNameRegistry` y presione **Entrar**.  
  
3.  En el panel de resultados, haga clic en el botón **Instalar** del primer resultado.  
  
4.  El paquete comenzará la descarga. Antes de agregarlo al proyecto, aparecerá el diálogo de aceptación de licencia. Si acepta los términos de licencia, haga clic en **Acepto**.  
  
5.  Los últimos ensamblados VINR se descargarán y agregarán al proyecto.  
  
#### <a name="downloading-the-validating-issuer-name-registry-by-using-the-package-manager-console"></a>Descargar el Registro de nombres del emisor que valida mediante la Consola del Administrador de paquetes  
  
1.  En Visual Studio, haga clic en **Herramientas**, **Administrador de paquetes de biblioteca** y, después, **Consola del Administrador de paquetes**.  
  
2.  Aparece la **Consola del Administrador de paquetes**. Escriba el texto siguiente y presione **Entrar**:  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.ValidatingIssuerNameRegistry  
    ```  
  
3.  Los últimos ensamblados VINR se descargarán y agregarán al proyecto.
