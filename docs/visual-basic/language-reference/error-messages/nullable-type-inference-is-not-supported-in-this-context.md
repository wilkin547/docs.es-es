---
title: No se admite la inferencia de tipos que acepten valores NULL en este contexto
ms.date: 07/20/2015
f1_keywords:
- vbc36629
- bc36629
helpviewer_keywords:
- BC36629
ms.assetid: 0a1e2dbc-d9a4-433d-9306-c5540782b81d
ms.openlocfilehash: f2d3bcdaccfd993da1eebf81ae961f35eb22b294
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90873682"
---
# <a name="nullable-type-inference-is-not-supported-in-this-context"></a>No se admite la inferencia de tipos que acepten valores NULL en este contexto

Los tipos de valor y las estructuras se pueden declarar como valores NULL.  
  
```vb  
Dim a? As Integer  
Dim b As Integer?  
```  
  
 Sin embargo, no puede utilizar la declaración que acepta valores NULL en combinación con la inferencia de tipos. En los ejemplos siguientes se produce este error.  
  
```vb  
' Not valid.  
' Dim c? = 10  
' Dim d? = a  
```  
  
 **Identificador de error:** BC36629  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
- Use una `As` cláusula para declarar la variable como un tipo de valor que acepta valores NULL.  
  
## <a name="see-also"></a>Consulte también

- [Tipos de valor que aceptan valores NULL](../../programming-guide/language-features/data-types/nullable-value-types.md)
- [Inferencia de tipo de variable local](../../programming-guide/language-features/variables/local-type-inference.md)
