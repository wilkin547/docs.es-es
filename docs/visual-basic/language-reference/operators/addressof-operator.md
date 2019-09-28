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
ms.openlocfilehash: 2ebadf5ded1a23fe46b8e16cf18ae265b5d3c255
ms.sourcegitcommit: 35da8fb45b4cca4e59cc99a5c56262c356977159
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/28/2019
ms.locfileid: "71591657"
---
# <a name="addressof-operator-visual-basic"></a>AddressOf (Operador) (Visual Basic)
Crea una instancia de delegado que hace referencia al procedimiento específico.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Elementos  
 `procedurename`  
 Obligatorio. Especifica el procedimiento al que debe hacer referencia el delegado recién creado.  
  
## <a name="remarks"></a>Comentarios  
 El operador `AddressOf` crea un delegado que apunta a la función Sub o especificada por `procedurename`. Cuando el procedimiento especificado es un método de instancia, el delegado hace referencia tanto a la instancia como al método. A continuación, cuando se invoca al delegado, se llama al método especificado de la instancia especificada.  
  
 El operador `AddressOf` se puede usar como operando de un constructor de delegado o en un contexto en el que el compilador puede determinar el tipo del delegado.  
  
## <a name="example"></a>Ejemplo  
 En este ejemplo se usa el operador `AddressOf` para designar un delegado que controle el evento `Click` de un botón.  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa el operador `AddressOf` para designar la función de inicio de un subproceso.  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Vea también

- [Declare (instrucción)](../../../visual-basic/language-reference/statements/declare-statement.md)
- [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)
- [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)
- [Delegados](../../../visual-basic/programming-guide/language-features/delegates/index.md)
