---
title: '&#39; IsNot &#39; operando de tipo &#39; typename &#39; solo se puede comparar a &#39; Nada &#39; porque &#39; typename &#39; es un tipo que acepta valores null'
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- bc32128
- vbc32128
helpviewer_keywords: BC32128
ms.assetid: 1155b23a-ad75-4bab-b9da-73f35c767a36
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: ec0ae1561bfbee998e7c65f6023012c0f982a8a7
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="39isnot39-operand-of-type-39typename39-can-only-be-compared-to-39nothing39-because-39typename39-is-a-nullable-type"></a>&#39; IsNot &#39; operando de tipo &#39; typename &#39; solo se puede comparar a &#39; Nada &#39; porque &#39; typename &#39; es un tipo que acepta valores null
Una variable declarada como que acepta valores NULL se ha comparado con una expresión distinta de `Nothing` mediante el `IsNot` operador.  
  
 **Id. de error:** BC32128  
  
## <a name="to-correct-this-error"></a>Para corregir este error  
  
1.  Para comparar un tipo que acepta valores NULL con una expresión distinta de `Nothing` mediante el uso de la `IsNot` operador, llame a la `GetType` método en el tipo que acepta valores NULL y compare el resultado a la expresión, tal como se muestra en el ejemplo siguiente.  
  
```vb  
Dim number? As Integer = 5  
  
If number IsNot Nothing Then  
  If number.GetType() IsNot Type.GetType("System.Int32") Then   
  
  End If  
End If  
```  
  
## <a name="see-also"></a>Vea también  
 [Tipos de valor que aceptan valores NULL](../../../visual-basic/programming-guide/language-features/data-types/nullable-value-types.md)  
 [IsNot (operador)](../../../visual-basic/language-reference/operators/isnot-operator.md)
