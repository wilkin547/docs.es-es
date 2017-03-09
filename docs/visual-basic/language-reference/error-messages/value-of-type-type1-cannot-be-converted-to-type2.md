---
title: "Un valor de tipo &#39;tipo1&#39; no se puede convertir en &#39;tipo2&#39; | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vbc31194"
  - "bc31194"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC31194"
ms.assetid: 03d50c31-addd-4c90-9c53-725b84f9782e
caps.latest.revision: 5
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 5
---
# Un valor de tipo &#39;tipo1&#39; no se puede convertir en &#39;tipo2&#39;
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Un valor de tipo 'tipo1' no se puede convertir en 'tipo2'Puede usar la propiedad 'Value' para obtener el valor de cadena del primer elemento de '\<parentElement\>'.  
  
 Se intentó convertir implícitamente un literal XML a un tipo específico.  El literal XML no se puede convertir implícitamente al tipo especificado.  
  
 **Id. de error:** BC31194  
  
### Para corregir este error  
  
-   Use la propiedad `Value` del literal XML para hacer referencia a su valor como `String`.  Use la función `CType`, otra función de conversión de tipo o la clase <xref:System.Convert> para convertir el valor como el tipo especificado.  
  
## Vea también  
 <xref:System.Convert>   
 [Funciones de conversión de tipos](../../../visual-basic/language-reference/functions/type-conversion-functions.md)   
 [Literales XML](../../../visual-basic/language-reference/xml-literals/index.md)   
 [XML](../../../visual-basic/programming-guide/language-features/xml/index.md)