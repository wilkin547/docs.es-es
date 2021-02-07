---
description: 'Más información acerca de: instrucción call (Visual Basic)'
title: Instrucción Call
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 70e6c109621c3710ad9476a952e9c384a142ba3d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99674017"
---
# <a name="call-statement-visual-basic"></a>Call (Instrucción, Visual Basic)

Transfiere el control a `Function` un `Sub` procedimiento de biblioteca de vínculos dinámicos (dll), o.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a>Partes  

|||
|---|---|
|`procedureName`|Necesario. Nombre del procedimiento al que se va a llamar.|
|`argumentList`|Opcional. Lista de variables o expresiones que representan los argumentos que se pasan al procedimiento cuando se llama. Los argumentos múltiples se separan mediante comas. Si incluye `argumentList` , debe encerrarlo entre paréntesis.|
|||
  
## <a name="remarks"></a>Observaciones

 Puede usar la `Call` palabra clave al llamar a un procedimiento. Para la mayoría de las llamadas a procedimientos, no es necesario usar esta palabra clave.

 Normalmente, se usa la `Call` palabra clave cuando la expresión llamada no comienza por un identificador. No se recomienda el uso de la `Call` palabra clave para otros usos.

 Si el procedimiento devuelve un valor, la `Call` instrucción lo descarta.

## <a name="example"></a>Ejemplo

 En el código siguiente se muestran dos ejemplos en los que la `Call` palabra clave es necesaria para llamar a un procedimiento. En ambos ejemplos, la expresión llamada no comienza por un identificador.

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a>Vea también

- [Instrucción Function](function-statement.md)
- [Instrucción Sub](sub-statement.md)
- [Declare Statement](declare-statement.md)
- [Expresiones lambda](../../programming-guide/language-features/procedures/lambda-expressions.md)
