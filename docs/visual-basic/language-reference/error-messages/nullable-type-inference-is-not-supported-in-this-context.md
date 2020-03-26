---
title: No se admite la inferencia de tipos que acepten valores NULL en este contexto
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: 42bde0b1843e52bbc16118bb056ade791591904e
ms.sourcegitcommit: 99b153b93bf94d0fecf7c7bcecb58ac424dfa47c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/25/2020
ms.locfileid: "80249505"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a>No se admite la inferencia de tipos que acepten valores NULL en este contexto
Los tipos de valor y las estructuras se pueden declarar que aceptan valores NULL.  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 Sin embargo, no puede usar la declaración que acepta valores NULL en combinación con la inferencia de tipos. Los siguientes ejemplos provocan este error.  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **ID de error:** BC36629  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Utilice `As` una cláusula para declarar la variable como un tipo de valor que acepta valores NULL.  
  
## <a name="see-also"></a>Vea también

- [Tipos de valores que aceptan valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)
- [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
