---
title: Función anidada no tiene una firma que es compatible con el delegado &#39; &lt;nombredelegado&gt;&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc36532
- bc36532
helpviewer_keywords:
- BC36532
ms.assetid: 493f292c-d81e-40ef-8b47-61f020571829
ms.openlocfilehash: abfda4ee6064ec9ea54b8a3c383d10f8263a1458
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54506412"
---
# <a name="nested-function-does-not-have-a-signature-that-is-compatible-with-delegate-39ltdelegatenamegt39"></a>Función anidada no tiene una firma que es compatible con el delegado &#39; &lt;nombredelegado&gt;&#39;
Una expresión lambda se asignó a un delegado que tiene una firma incompatible. Por ejemplo, en el código siguiente, el delegado `Del` tiene dos parámetros enteros.  
  
```vb  
Delegate Function Del(ByVal p As Integer, ByVal q As Integer) As Integer  
```  
  
 Se produce el error si una expresión lambda con un argumento se declara como tipo `Del`:  
  
```vb  
' Neither of these is valid.   
' Dim lambda1 As Del = Function(n As Integer) n + 1  
' Dim lambda2 As Del = Function(n) n + 1  
```  
  
 **Identificador de error:** BC36532  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
-   Ajuste la definición del delegado o la expresión lambda asignada para que las firmas son compatibles.  
  
## <a name="see-also"></a>Vea también
- [Conversión de delegado flexible](../../../visual-basic/programming-guide/language-features/delegates/relaxed-delegate-conversion.md)
- [Expresiones lambda](../../../visual-basic/programming-guide/language-features/procedures/lambda-expressions.md)
