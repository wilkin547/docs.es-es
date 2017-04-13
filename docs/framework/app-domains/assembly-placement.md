---
title: "Colocaci&#243;n de ensamblados | Microsoft Docs"
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
  - "<codeBase> (elemento)"
  - "ensamblados [.NET Framework], ubicación"
  - "ensamblados [.NET Framework], colocación"
  - "ubicar ensamblados"
ms.assetid: ff8d48bc-f606-484f-9fe1-d0af264269fb
caps.latest.revision: 9
author: "rpetrusha"
ms.author: "ronpet"
manager: "wpickett"
caps.handback.revision: 9
---
# Colocaci&#243;n de ensamblados
En la mayoría de las aplicaciones .NET Framework, los ensamblados que componen una aplicación se colocan en el directorio de la aplicación, en un subdirectorio de este último o en la caché global de ensamblados \(si el ensamblado está compartido\).  Para reemplazar la ubicación en la que Common Language Runtime busca un ensamblado, utilice [Elemento \<codeBase\>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) en un archivo de configuración.  Si el ensamblado no tiene un nombre seguro, la ubicación especificada mediante [Elemento \<codeBase\>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) se limita al directorio de la aplicación o a un subdirectorio de éste.  Si el ensamblado tiene un nombre seguro, [Elemento \<codeBase\>](../../../docs/framework/configure-apps/file-schema/runtime/codebase-element.md) puede especificar cualquier ubicación en el equipo o la red.  
  
 Se aplican reglas similares a la búsqueda de ensamblados cuando se trabaja con código no administrado o aplicaciones de interoperabilidad COM: si el ensamblado va a compartirse entre varias aplicaciones, debe instalarse en la caché global de ensamblados.  Los ensamblados que se utilizan con código no administrado deben exportarse como biblioteca de tipos y registrarse.  Los ensamblados utilizados por la interoperabilidad COM deben registrarse en el catálogo, aunque, en algunos casos, este registro es automático.  
  
## Vea también  
 [Cómo el motor en tiempo de ejecución ubica ensamblados](../../../docs/framework/deployment/how-the-runtime-locates-assemblies.md)   
 [Configurar aplicaciones](../../../docs/framework/configure-apps/index.md)   
 [Advanced COM Interoperability](http://msdn.microsoft.com/es-es/3ada36e5-2390-4d70-b490-6ad8de92f2fb)   
 [Ensamblados en Common Language Runtime](../../../docs/framework/app-domains/assemblies-in-the-common-language-runtime.md)