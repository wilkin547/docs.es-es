---
title: "No se puede hacer referencia a &#39;&lt;nombre&gt;&#39; porque es miembro del campo de tipo de valor &#39;&lt;nombre&gt;&#39; de la clase &#39;&lt;nombreDeClase&gt;&#39; que tiene &#39;System.MarshalByRefObject&#39; como clase base | Microsoft Docs"
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
  - "vbc30310"
  - "bc30310"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30310"
ms.assetid: 2aeb8872-7c87-4f01-98ef-9714ba3eebbe
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# No se puede hacer referencia a &#39;&lt;nombre&gt;&#39; porque es miembro del campo de tipo de valor &#39;&lt;nombre&gt;&#39; de la clase &#39;&lt;nombreDeClase&gt;&#39; que tiene &#39;System.MarshalByRefObject&#39; como clase base
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

La clase `System.MarshalByRefObject` habilita las aplicaciones que admiten el acceso remoto a los objetos en los límites de dominio de aplicación.  Los tipos deben heredar de la clase `MarshalByRejectObject` cuando se utilicen en los límites de dominio de aplicación.  No se debe copiar el estado del objeto, ya que los miembros del objeto no se pueden utilizar fuera del dominio de aplicación en el que se han creado.  
  
 **Identificador de error:** BC30310  
  
### Para corregir este error  
  
1.  Compruebe la referencia para asegurarse de que el miembro al que se está haciendo referencia es válido.  
  
2.  Califique explícitamente el miembro con la palabra clave `Me`.  
  
## Vea también  
 <xref:System.MarshalByRefObject>   
 [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md)