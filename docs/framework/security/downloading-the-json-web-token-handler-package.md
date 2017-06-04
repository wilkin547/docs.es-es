---
title: "Descargar el paquete del controlador de token web de JSON | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-clr"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: d12b3f5b-f1f1-4a9d-a159-0c13e5976c90
caps.latest.revision: 3
author: "wadepickett"
ms.author: "wpickett"
manager: "wpickett"
caps.handback.revision: 3
---
# Descargar el paquete del controlador de token web de JSON
En este tema se explica cómo descargar y usar el controlador de token web JSON en el proyecto.  
  
## Descargar el controlador de token web JSON  
 La extensión del controlador de token web JSON está disponible como paquete NuGet, que agrega los ensamblados y referencias necesarios al proyecto.  Si aún no tiene NuGet instalado, vaya a [nuget.org](http://nuget.org) para instalarlo.  Puede ver el historial de creación de versiones para la extensión si visita su página en NuGet: [Controlador simbólico web JSON en NuGet](http://www.nuget.org/packages/System.IdentityModel.Tokens.Jwt/)  
  
#### Descargar el controlador de token web JSON mediante la GUI del Administrador de paquetes  
  
1.  En Visual Studio, haga clic con el botón secundario en el proyecto en el **Explorador de soluciones** y, a continuación, seleccione **Administrar paquetes NuGet**.  
  
2.  En la ventana **Administrar paquetes NuGet**, haga clic en el cuadro de búsqueda y escriba `JWT Token Handler` y presione **Entrar**.  
  
3.  En el panel de resultados, haga clic en el botón **Instalar** del primer resultado.  
  
4.  El paquete comenzará la descarga.  Antes de agregarlo al proyecto, aparecerá el diálogo de aceptación de licencia.  Si acepta los términos de licencia, haga clic en **Acepto**.  
  
5.  Los últimos ensamblados de controlador de token web JSON se descargarán y agregarán al proyecto.  
  
#### Descargar el controlador de token web JSON mediante la Consola del Administrador de paquetes  
  
1.  En Visual Studio, haga clic en **Herramientas**, **Administrador de paquetes de biblioteca** y, a continuación, **Consola del Administrador de paquetes**.  
  
2.  Aparece la **Consola del Administrador de paquetes**.  Escriba el texto y presione **Intro**:  
  
    ```powershell  
    Install-Package System.IdentityModel.Tokens.Jwt  
    ```  
  
3.  Los últimos ensamblados de controlador de token web JSON se descargarán y agregarán al proyecto.