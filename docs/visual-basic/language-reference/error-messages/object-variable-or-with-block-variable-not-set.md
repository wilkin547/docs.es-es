---
title: "Variable de objeto o de bloque With no establecida | Microsoft Docs"
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
  - "vbrID91"
dev_langs: 
  - "VB"
ms.assetid: 2f03e611-f0ed-465c-99a2-a816e034faa3
caps.latest.revision: 9
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Variable de objeto o de bloque With no establecida
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Se está haciendo referencia a una variable no válida.  Para crear una variable de objeto, declárela y asígnele una referencia válida con la instrucción `Set`.  De forma similar, un bloque `With...End With` se debe inicializar ejecutando el punto de entrada de la instrucción `With`.  
  
### Para corregir este error  
  
1.  Compruebe que la variable de objeto hace referencia a un objeto válido y especifique o vuelva a especificar una referencia al objeto.  
  
2.  Asegúrese de no utilizar un conjunto de variables de objeto definido en `Nothing`.  
  
3.  Compruebe que la biblioteca de objetos donde se ha descrito el objeto se ha seleccionado en el cuadro de diálogo `Add References`.  
  
4.  Asegúrese de que el bloque `With` se ha inicializado ejecutando el punto de entrada de la instrucción `With`.  
  
## Vea también  
 [Declaración de variables de objeto](../../../visual-basic/programming-guide/language-features/variables/object-variable-declaration.md)   
 [With...End With \(Instrucción\)](../../../visual-basic/language-reference/statements/with-end-with-statement.md)