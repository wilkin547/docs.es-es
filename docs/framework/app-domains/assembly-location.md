---
title: "Ubicaci&#243;n del ensamblado | Microsoft Docs"
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
  - "ensamblados [.NET Framework], ubicación"
  - "ubicar ensamblados"
ms.assetid: 9f1f41a7-2954-49d3-a2c0-62b6ef4d40ab
caps.latest.revision: 7
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 7
---
# Ubicaci&#243;n del ensamblado
La ubicación de un ensamblado determina si Common Language Runtime lo encuentra cuando se hace referencia a él y también puede determinar si otros ensamblados pueden compartirlo.  Un ensamblado se puede implementar en las siguientes ubicaciones:  
  
-   El directorio o subdirectorios de la aplicación.  
  
     Es la ubicación de implementación más frecuente de los ensamblados.  Los subdirectorios del directorio raíz de una aplicación se pueden basar en el idioma o en la referencia cultural.  Si un ensamblado tiene información en el atributo de referencia cultural, tiene que estar en un subdirectorio del directorio de la aplicación con el nombre de esa referencia cultural.  
  
-   La caché global de ensamblados.  
  
     Es una caché de código para todo el equipo que se instala donde esté instalado Common Language Runtime.  En la mayoría de los casos, si se piensa compartir un ensamblado con varias aplicaciones, habrá que instalarlo en la caché global de ensamblados.  
  
-   Un servidor HTTP.  
  
     Un ensamblado instalado en un servidor HTTP debe tener un nombre seguro, y se señala en la sección del código base del archivo de configuración de la aplicación.  
  
## Vea también  
 [Crear ensamblados](../../../docs/framework/app-domains/create-assemblies.md)   
 [Caché global de ensamblados](../../../docs/framework/app-domains/gac.md)   
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Programar con ensamblados](../../../docs/framework/app-domains/programming-with-assemblies.md)