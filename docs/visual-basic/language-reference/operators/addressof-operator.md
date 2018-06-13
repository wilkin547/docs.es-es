---
title: AddressOf (Operador) (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 7c229c32a3b295b4dbfe50ca2abc60d4ad5f2145
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33597792"
---
# <a name="addressof-operator-visual-basic"></a>AddressOf (Operador) (Visual Basic)
Crea una instancia de delegado de procedimiento que hace referencia el procedimiento específico.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Elementos  
 `procedurename`  
 Requerido. Especifica el procedimiento que hace referencia el delegado de procedimiento recién creado.  
  
## <a name="remarks"></a>Comentarios  
 El `AddressOf` operador crea un delegado de función que apunta a la función especificada por `procedurename`. Cuando el procedimiento especificado es que un método de instancia, a continuación, el delegado de función hace referencia a la instancia y el método. A continuación, cuando se invoca el delegado de función se llama al método especificado de la instancia especificada.  
  
 El `AddressOf` operador puede utilizarse como operando de un constructor de delegado o se puede utilizar en un contexto en el que se puede determinar el tipo de delegado por el compilador.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se utiliza la `AddressOf` operador para designar un delegado para controlar el `Click` eventos de un botón.  
  
 [!code-vb[VbVbalrDelegates#8](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_1.vb)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `AddressOf` operador para designar la función de inicio para un subproceso.  
  
 [!code-vb[VbVbalrDelegates#9](../../../visual-basic/language-reference/operators/codesnippet/VisualBasic/addressof-operator_2.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
 [Delegados](../../../visual-basic/programming-guide/language-features/delegates/index.md)
