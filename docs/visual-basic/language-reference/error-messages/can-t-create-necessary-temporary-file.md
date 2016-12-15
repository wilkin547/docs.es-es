---
title: "No se puede crear el archivo temporal necesario | Microsoft Docs"
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
  - "vbrID322"
dev_langs: 
  - "VB"
ms.assetid: 53617b5b-eb06-4188-b4c2-8607cb9fbc79
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# No se puede crear el archivo temporal necesario
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

O la unidad que contiene el directorio especificado por la variable de entorno TEMP está completa, o la variable de entorno TEMP especifica una unidad o un directorio no válido o de sólo lectura.  
  
### Para corregir este error  
  
1.  Elimine archivos de la unidad, si está completa.  
  
2.  Indique otra unidad en la variable de entorno TEMP.  
  
3.  Indique una unidad válida para la variable de entorno TEMP.  
  
4.  Quite la restricción de sólo lectura de la unidad o el directorio actualmente especificado.  
  
## Vea también  
 [Tipos de error](../../../visual-basic/programming-guide/language-features/error-types.md)