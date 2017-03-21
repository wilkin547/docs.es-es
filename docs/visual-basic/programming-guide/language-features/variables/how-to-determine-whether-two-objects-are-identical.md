---
title: "Cómo: determinar si dos objetos son idénticos (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- testing, objects
- objects [Visual Basic], comparing
- object variables, determining identity
ms.assetid: 7829f817-0d1f-4749-a707-de0b95e0cf5c
caps.latest.revision: 19
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 3a853d9f958829eeb0fb42ecbcdae7ba912c89ed
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-determine-whether-two-objects-are-identical-visual-basic"></a>Cómo: Determinar si dos objetos son idénticos (Visual Basic)
En [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)], dos referencias de variable se consideran idénticas si sus punteros son los mismos, es decir, si ambas variables señalan a la misma instancia de clase en la memoria. Por ejemplo, en una aplicación de formularios Windows Forms, puede realizar una comparación para determinar si la instancia actual (`Me`) es igual a una instancia concreta, como `Form2`.  
  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)]proporciona dos operadores para comparar los punteros. El [operador Is](../../../../visual-basic/language-reference/operators/is-operator.md) devuelve `True` si los objetos son idénticos y el [IsNot (operador)](../../../../visual-basic/language-reference/operators/isnot-operator.md) devuelve `True` si no lo son.  
  
## <a name="determining-if-two-objects-are-identical"></a>Determinar si dos objetos son idénticos  
  
#### <a name="to-determine-if-two-objects-are-identical"></a>Para determinar si dos objetos son idénticos  
  
1.  Configurar un `Boolean` expresión para probar los dos objetos.  
  
2.  En la expresión de prueba, utilice la `Is` operador con los dos objetos como operandos.  
  
     `Is`Devuelve `True` si los objetos señalan a la misma instancia de clase.  
  
## <a name="determining-if-two-objects-are-not-identical"></a>Determinar si dos objetos no son idénticos  
 En ocasiones, deseará realizar una acción si los dos objetos no son idénticos, y puede ser complicado combinar `Not` y `Is`, por ejemplo `If Not obj1 Is obj2`. En este caso puede utilizar el `IsNot` operador.  
  
#### <a name="to-determine-if-two-objects-are-not-identical"></a>Para determinar si dos objetos no son idénticos  
  
1.  Configurar un `Boolean` expresión para probar los dos objetos.  
  
2.  En la expresión de prueba, utilice la `IsNot` operador con los dos objetos como operandos.  
  
     `IsNot`Devuelve `True` si los objetos no señalan a la misma instancia de clase.  
  
## <a name="example"></a>Ejemplo  
 El ejemplo siguiente prueba pares de `Object` las variables para ver si señalan a la misma instancia de clase.  
  
 [!code-vb[VbVbalrKeywords&#14;](../../../../visual-basic/language-reference/codesnippet/VisualBasic/how-to-determine-whether-two-objects-are-identical_1.vb)]  
  
 El ejemplo anterior muestra el siguiente resultado.  
  
 `objA different from objB? True`  
  
 `objA identical to objC? True`  
  
## <a name="see-also"></a>Vea también  
 [Tipo de datos de objeto](../../../../visual-basic/language-reference/data-types/object-data-type.md)   
 [Variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variables.md)   
 [Valores de variables de objeto](../../../../visual-basic/programming-guide/language-features/variables/object-variable-values.md)   
 [Is (operador)](../../../../visual-basic/language-reference/operators/is-operator.md)   
 [IsNot (operador)](../../../../visual-basic/language-reference/operators/isnot-operator.md)   
 [Cómo: determinar si dos objetos están relacionados](../../../../visual-basic/programming-guide/language-features/variables/how-to-determine-whether-two-objects-are-related.md)   
 [Me, My, MyBase y MyClass](../../../../visual-basic/programming-guide/program-structure/me-my-mybase-and-myclass.md)
