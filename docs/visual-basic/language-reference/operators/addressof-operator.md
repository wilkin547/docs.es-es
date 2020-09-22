---
title: Operador AddressOf
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: edce7d4a2268bd311045ea4972672fe8fd2600ea
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/22/2020
ms.locfileid: "90874888"
---
# <a name="addressof-operator-visual-basic"></a>AddressOf (Operador) (Visual Basic)

Crea una instancia de delegado que hace referencia al procedimiento específico.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Partes  

 `procedurename`  
 Obligatorio. Especifica el procedimiento al que debe hacer referencia el delegado recién creado.  
  
## <a name="remarks"></a>Comentarios  

 El `AddressOf` operador crea un delegado que apunta a la función Sub o especificada por `procedurename` . Cuando el procedimiento especificado es un método de instancia, el delegado hace referencia tanto a la instancia como al método. A continuación, cuando se invoca al delegado, se llama al método especificado de la instancia especificada.  
  
 El `AddressOf` operador se puede usar como operando de un constructor de delegado o en un contexto en el que el compilador puede determinar el tipo del delegado.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usa el `AddressOf` operador para designar un delegado para controlar el `Click` evento de un botón.  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa el `AddressOf` operador para designar la función de inicio de un subproceso.  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Consulte también

- [Declare Statement](../statements/declare-statement.md)
- [Instrucción Function](../statements/function-statement.md)
- [Instrucción Sub](../statements/sub-statement.md)
- [Delegados](../../programming-guide/language-features/delegates/index.md)
