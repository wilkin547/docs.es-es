---
title: "Utilizar componentes con servicio junto con la memoria cach&#233; global de ensamblados | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-bcl"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ensamblados [.NET Framework], caché global de ensamblados"
  - "GAC (caché global de ensamblados), componentes con servicio"
  - "caché global de ensamblados, componentes con servicio"
  - "componentes con servicio, caché global de ensamblados"
ms.assetid: 3423e5d9-234c-4571-8161-e35f6d130128
caps.latest.revision: 8
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 6
---
# Utilizar componentes con servicio junto con la memoria cach&#233; global de ensamblados
Los componentes con servicio \(componentes COM\+ de código administrado\) se deben colocar en la caché global de ensamblados.  En algunos escenarios, Common Language Runtime y los Servicios COM\+ pueden controlar componentes con servicio que no estén en la caché global de ensamblados, pero en otros escenarios no pueden hacerlo.  Esto se ilustra en los siguientes escenarios.  
  
-   Para los componentes con servicio de una aplicación de servidor COM\+, el ensamblado que contiene los componentes debe estar en la caché global de ensamblados porque Dllhost.exe no se ejecuta en el mismo directorio que el que contiene los componentes con servicio.  
  
-   Para los componentes con servicio de una aplicación de biblioteca COM\+, el motor en tiempo de ejecución y los Servicios COM\+ pueden resolver la referencia al ensamblado que contiene los componentes haciendo una búsqueda en el directorio actual.  En este caso, no hace falta que el ensamblado esté en la caché global de ensamblados.  
  
-   Para los componentes con servicio de una aplicación de ASP.NET, la situación es distinta.  Si el ensamblado que contiene los componentes con servicio se ubica en el directorio bin en la base de aplicación y se utiliza el registro a petición, se hará una copia en segundo plano del ensamblado en la caché de descarga porque ASP.NET aprovecha las capacidades de copia del motor en tiempo de ejecución.  
  
## Vea también  
 [How to: Create a Serviced Component](http://msdn.microsoft.com/es-es/7ec0b488-e5fc-46f2-a48d-1278ea4e301d)   
 [Trabajar con ensamblados y la memoria caché global de ensamblados](../../../docs/framework/app-domains/working-with-assemblies-and-the-gac.md)   
 [Gacutil.exe \(Global Assembly Cache Tool\)](../../../docs/framework/tools/gacutil-exe-gac-tool.md)   
 [Assembly Cache Viewer \(Shfusion.dll\)](http://msdn.microsoft.com/es-es/0d9464cf-ddba-4ca9-bbec-f678fb58f380)