---
title: El nombre de una variable de rango sólo se puede inferir a partir de un nombre simple o completo sin argumentos
ms.date: 07/20/2015
f1_keywords:
- vbc36599
- bc36599
helpviewer_keywords:
- BC36599
ms.assetid: 17763dbe-f74f-4ccb-8086-cb7e45ec4d12
ms.openlocfilehash: 344a813907483dcb0e9f531b54db68a88d77f3dc
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2019
ms.locfileid: "58842387"
---
# <a name="range-variable-name-can-be-inferred-only-from-a-simple-or-qualified-name-with-no-arguments"></a>El nombre de una variable de rango sólo se puede inferir a partir de un nombre simple o completo sin argumentos
Se incluye un elemento de programación que toma uno o más argumentos en una consulta LINQ. El compilador no puede inferir una variable de rango de ese elemento de programación.  
  
 **Identificador de error:** BC36599  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Proporcione un nombre de variable explícito para el elemento de programación, como se muestra en el código siguiente:  
  
```  
Dim query = From var1 In collection1   
            Select VariableAlias= SampleFunction(var1), var1  
```  
  
## <a name="see-also"></a>Vea también

- [Introducción a LINQ en Visual Basic](../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
- [Select (cláusula)](../../../visual-basic/language-reference/queries/select-clause.md)
