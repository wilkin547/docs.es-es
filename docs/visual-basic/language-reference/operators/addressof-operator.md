---
title: AddressOf (operador) (Visual Basic) | Documentos de Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- AddressOf
- vb.AddressOf
dev_langs:
- VB
helpviewer_keywords:
- AddressOf operator
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
caps.latest.revision: 11
author: dotnet-bot
ms.author: dotnetcontent
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
ms.openlocfilehash: 04a7c5be9b890faea561c28715093a271cf9eaa8
ms.lasthandoff: 03/13/2017

---
# <a name="addressof-operator-visual-basic"></a>AddressOf (Operador) (Visual Basic)
Crea una instancia de delegado de procedimiento que hace referencia el procedimiento especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Elementos  
 `procedurename`  
 Obligatorio. Especifica el procedimiento que hace referencia el delegado de procedimiento recién creado.  
  
## <a name="remarks"></a>Comentarios  
 El `AddressOf` operador crea una función delegada que apunta a la función especificada por `procedurename`. Cuando el procedimiento especificado es que un método de instancia, la función delegada hace referencia a la instancia y el método. A continuación, cuando se invoca el delegado de función se llama al método especificado de la instancia especificada.  
  
 El `AddressOf` operador puede utilizarse como operando de un constructor delegado o se puede utilizar en un contexto en el que se puede determinar el tipo del delegado por el compilador.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la `AddressOf` operador para designar un delegado para controlar el `Click` eventos de un botón.  
  
 [!code-vb[VbVbalrDelegates Nº&8;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `AddressOf` operador para designar la función de inicio de un subproceso.  
  
 [!code-vb[VbVbalrDelegates&#9;](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)   
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Delegados](../../../visual-basic/programming-guide/language-features/delegates/index.md)
