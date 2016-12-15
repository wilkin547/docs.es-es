---
title: "&#39;&lt;nombre de tipo&gt;&#39; no puede heredar del &lt;tipo&gt; &#39;&lt;nombre de tipo base&gt;&#39; porque ampl&#237;a el acceso del &lt;tipo&gt; fuera del ensamblado | Microsoft Docs"
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
  - "vbc30910"
  - "bc30910"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "BC30910"
ms.assetid: 68fc05c5-5d55-4742-9a3b-ea04312594f4
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;nombre de tipo&gt;&#39; no puede heredar del &lt;tipo&gt; &#39;&lt;nombre de tipo base&gt;&#39; porque ampl&#237;a el acceso del &lt;tipo&gt; fuera del ensamblado
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Una clase o interfaz hereda de una clase base o interfaz, pero tiene un nivel de acceso menos restrictivo.  
  
 Por ejemplo, una interfaz `Public` hereda de una interfaz `Friend` o una clase `Protected` hereda de una clase `Private`.  Esto expone la clase base o interfaz para obtener acceso más allá del nivel deseado.  
  
 **Identificador de error:** BC30910  
  
### Para corregir este error  
  
-   Cambie el nivel de acceso de la clase derivada o interfaz para que sea al menos tan restrictivo como el de la clase base o interfaz.  
  
     O bien  
  
-   Si requiere el nivel de acceso menos restrictivo, quite la instrucción `Inherits`.  No puede heredar de una clase base o interfaz más restringida.  
  
## Vea también  
 [Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Interface \(Instrucción\)](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Inherits \(Instrucción\)](../../../visual-basic/language-reference/statements/inherits-statement.md)   
 [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md)