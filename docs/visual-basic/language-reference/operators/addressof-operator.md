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
ms.openlocfilehash: 098ca95687d8b0e9f4ac90d5c7e0df9a9a0ad950
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67760379"
---
# <a name="addressof-operator-visual-basic"></a>AddressOf (Operador) (Visual Basic)
Crea una instancia de delegado que hace referencia el procedimiento específico.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Elementos  
 `procedurename`  
 Necesario. Especifica el procedimiento que hace referencia el delegado recién creado.  
  
## <a name="remarks"></a>Comentarios  
 El `AddressOf` operador crea un delegado que apunta a la función especificada por o a sub `procedurename`. Cuando el procedimiento especificado es un método de instancia, a continuación, el delegado que hace referencia a la instancia y el método. A continuación, cuando se invoca el delegado se llama al método especificado de la instancia especificada.  
  
 El `AddressOf` operador puede utilizarse como operando de un constructor de delegado o se puede usar en un contexto en el que se puede determinar el tipo del delegado por el compilador.  
  
## <a name="example"></a>Ejemplo  
 Este ejemplo se usa el `AddressOf` operador para designar un delegado para controlar el `Click` eventos de un botón.  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el `AddressOf` operador para designar la función de inicio de un subproceso.  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Vea también

- [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Delegados](../../../visual-basic/programming-guide/language-features/delegates/index.md)
