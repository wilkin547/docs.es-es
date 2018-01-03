---
title: "Una matriz declarada como variable de control de bucle no se puede declarar con un tamaño inicial"
ms.date: 07/20/2015
ms.prod: .net
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc32039
- bc32039
helpviewer_keywords: BC32039
ms.assetid: 1d8b6560-c9eb-4b71-a038-24c6f5a5ce46
caps.latest.revision: "13"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ef36f14d5323a4592afe59573e249d8cfb218df9
ms.sourcegitcommit: 34ec7753acf76f90a0fa845235ef06663dc9e36e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/21/2017
---
# <a name="array-declared-as-for-loop-control-variable-cannot-be-declared-with-an-initial-size"></a>Una matriz declarada como variable de control de bucle no se puede declarar con un tamaño inicial
A `For Each` bucle utiliza una matriz como su *elemento* variable de iteración pero inicializa esa matriz.  
  
 Las instrucciones siguientes muestran cómo se puede generar este error.  
  
```  
Dim arrayList As New List(Of Integer())  
For Each listElement() As Integer In arrayList  
For Each listElement(1) As Integer In arrayList  
```  
  
 La primera `For Each` instrucción es la manera correcta de tener acceso a elementos de `arrayList`. El segundo `For Each` instrucción genera este error.  
  
 **Id. de error:** BC32039  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Quite la inicialización de la declaración de la *elemento* variable de iteración.  
  
## <a name="see-also"></a>Vea también  
 [For...Next (instrucción)](../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Matrices](../../../visual-basic/programming-guide/language-features/arrays/index.md)  
 [Colecciones](../../../standard/collections/index.md)
