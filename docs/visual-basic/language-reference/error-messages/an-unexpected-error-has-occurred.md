---
title: "Error inesperado porque no se puede conseguir un recurso del sistema operativo necesario para el inicio de una instancia &#250;nica | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbrAppModel_CantGetMemoryMappedFile"
dev_langs: 
  - "VB"
ms.assetid: 0d9f2a30-ff72-4355-8060-744f22339359
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Error inesperado porque no se puede conseguir un recurso del sistema operativo necesario para el inicio de una instancia &#250;nica
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La aplicación no pudo obtener un recurso de sistema operativo necesario.  Algunas de las posibles causas de este problema son:  
  
-   La aplicación no tiene permisos para crear objetos de sistema operativo con nombre.  
  
-   Common Language Runtime no tiene permisos para crear archivos asignados a memoria.  
  
-   La aplicación necesita acceder a un objeto de sistema operativo, pero hay otro proceso que lo está utilizando.  
  
### Para corregir este error  
  
1.  Confirme que la aplicación tiene permisos suficientes para crear objetos de sistema operativo con nombre.  
  
2.  Confirme que Common Language Runtime tiene permisos suficientes para crear archivos asignados a memoria.  
  
3.  Reinicie el equipo para borrar cualquier proceso que pueda estar haciendo uso del recurso necesario para conectarse a la aplicación de instancia original.  
  
4.  Anote las circunstancias en las que se ha produjo el error y llame a los Servicios de soporte técnico de Microsoft.  
  
## Vea también  
 [Aplicación \(Página, Diseñador de proyectos\) \(Visual Basic\)](/visual-studio/ide/reference/application-page-project-designer-visual-basic)   
 [Conceptos básicos del depurador](/visual-studio/debugger/debugger-basics)   
 [Hable con nosotros](/visual-studio/ide/talk-to-us)