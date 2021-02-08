---
description: 'Más información acerca de: operador AddressOf (Visual Basic)'
title: Operador AddressOf
ms.date: 07/20/2015
f1_keywords:
- AddressOf
- vb.AddressOf
helpviewer_keywords:
- AddressOf operator [Visual Basic]
- addresses, passing to API procedures
ms.assetid: 8105a59d-60d8-4ab5-b221-5899cdfacbf4
ms.openlocfilehash: 2aba8c26aa9581fe1070574b8c408e09bf063d1f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774387"
---
# <a name="addressof-operator-visual-basic"></a>AddressOf (Operador) (Visual Basic)

Crea una instancia de delegado que hace referencia al procedimiento específico.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
AddressOf procedurename  
```  
  
## <a name="parts"></a>Partes  

 `procedurename`  
 Necesario. Especifica el procedimiento al que debe hacer referencia el delegado recién creado.  
  
## <a name="remarks"></a>Observaciones  

 El `AddressOf` operador crea un delegado que apunta a la función Sub o especificada por `procedurename` . Cuando el procedimiento especificado es un método de instancia, el delegado hace referencia tanto a la instancia como al método. A continuación, cuando se invoca al delegado, se llama al método especificado de la instancia especificada.  
  
 El `AddressOf` operador se puede usar como operando de un constructor de delegado o en un contexto en el que el compilador puede determinar el tipo del delegado.  
  
## <a name="example"></a>Ejemplo  

 En este ejemplo se usa el `AddressOf` operador para designar un delegado para controlar el `Click` evento de un botón.  
  
 [!code-vb[VbVbalrDelegates#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#8)]  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa el `AddressOf` operador para designar la función de inicio de un subproceso.  
  
 [!code-vb[VbVbalrDelegates#9](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrDelegates/VB/Class1.vb#9)]  
  
## <a name="see-also"></a>Vea también

- [Declare Statement](../statements/declare-statement.md)
- [Instrucción Function](../statements/function-statement.md)
- [Instrucción Sub](../statements/sub-statement.md)
- [Delegados](../../programming-guide/language-features/delegates/index.md)
