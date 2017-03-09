---
title: "Assembly (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Assembly"
  - "vb.AssemblyAttribute"
  - "Assembly"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Assembly (palabra clave)"
  - "Assembly (modificador)"
  - "bloques de atributos, Assembly (palabra clave)"
ms.assetid: 925e7471-3bdf-4b51-bb93-cbcfc6efc52f
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Assembly (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica que un atributo situado al comienzo de un archivo de código fuente se aplica a todo el ensamblado.  
  
## Comentarios  
 Muchos atributos se aplican a un elemento de programación individual, como una clase o propiedad.  Para incluir estos atributos, se adjunta el bloque de atributos, entre corchetes angulares \(`< >`\), directamente a la instrucción de declaración.  
  
 Si un atributo no pertenece únicamente al elemento que le sigue sino a todo el ensamblado completo, sitúe el bloque de atributos al principio del archivo de código fuente e identifique el atributo con la palabra clave `Assembly`.  Si se aplica al módulo de ensamblado actual, utilice la palabra clave [Module](../../../visual-basic/language-reference/modifiers/module-keyword.md).  
  
 También puede aplicar un atributo a un ensamblado en el archivo AssemblyInfo.vb, en cuyo caso no es necesario que utilice un bloque de atributos en el archivo de código fuente principal.  
  
## Vea también  
 [Module \<palabra clave\>](../../../visual-basic/language-reference/modifiers/module-keyword.md)   
 [Atributos](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)