---
title: "Module &lt;palabra clave&gt; (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ModuleAttribute"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "bloques de atributos, Module (palabra clave)"
  - "Module (palabra clave)"
  - "Module (modificador)"
ms.assetid: d971b940-05ab-4d56-8485-e3b8a661906b
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 13
---
# Module &lt;palabra clave&gt; (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica que un atributo situado al principio de un archivo de código fuente se aplica al módulo de ensamblado actual.  
  
## Comentarios  
 Muchos atributos se aplican a un elemento de programación individual, como una clase o propiedad.  Para incluir estos atributos, se adjunta el bloque de atributos, entre corchetes angulares \(`< >`\), directamente a la instrucción de declaración.  
  
 Si un atributo no sólo se aplica al siguiente elemento sino al módulo de ensamblado actual, el bloque de atributos se sitúa al principio del archivo de código fuente y el atributo se identifica con la palabra clave `Module`.  Si se aplica al ensamblado completo, utiliza la palabra clave [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md).  
  
 La palabra clave `Module` no es lo mismo que [Module \(Instrucción\)](../../../visual-basic/language-reference/statements/module-statement.md).  
  
## Vea también  
 [Assembly](../../../visual-basic/language-reference/modifiers/assembly.md)   
 [Module \(Instrucción\)](../../../visual-basic/language-reference/statements/module-statement.md)   
 [Atributos](../Topic/Attributes%20\(C%23%20and%20Visual%20Basic\).md)