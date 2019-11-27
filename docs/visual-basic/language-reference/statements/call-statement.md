---
title: Call (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- vb.Call
helpviewer_keywords:
- procedures [Visual Basic], Call statement
- Call statement [Visual Basic]
- procedures [Visual Basic], calling
ms.assetid: e5b31571-6867-406f-b8e7-a3f9aae4723a
ms.openlocfilehash: 7de194ea23827e08c49f4519c1000708a4bd91b4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350162"
---
# <a name="call-statement-visual-basic"></a>Call (Instrucción, Visual Basic)

Transfiere el control a un procedimiento de biblioteca de vínculos dinámicos (DLL) de `Function`, `Sub`o.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
[ Call ] procedureName [ (argumentList) ]  
```  
  
## <a name="parts"></a>Elementos  

|||
|---|---|
|`procedureName`|Obligatorio. Nombre del procedimiento al que se va a llamar.|
|`argumentList`|Opcional. Lista de variables o expresiones que representan los argumentos que se pasan al procedimiento cuando se llama. Los argumentos múltiples se separan mediante comas. Si incluye `argumentList`, debe encerrarlo entre paréntesis.|
|||
  
## <a name="remarks"></a>Comentarios

 Puede usar la palabra clave `Call` al llamar a un procedimiento. Para la mayoría de las llamadas a procedimientos, no es necesario usar esta palabra clave.

 Normalmente se usa la palabra clave `Call` cuando la expresión llamada no comienza por un identificador. No se recomienda el uso de la palabra clave `Call` para otros usos.

 Si el procedimiento devuelve un valor, la instrucción `Call` lo descarta.

## <a name="example"></a>Ejemplo

 En el código siguiente se muestran dos ejemplos en los que la palabra clave `Call` es necesaria para llamar a un procedimiento. En ambos ejemplos, la expresión llamada no comienza por un identificador.

 [!code-vb[VbVbalrStatements#97](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#97)]  
  
## <a name="see-also"></a>Vea también

- [Function (instrucción)](function-statement.md)
- [Sub (instrucción)](sub-statement.md)
- [Declare (instrucción)](declare-statement.md)
- [Expresiones lambda](../../programming-guide/language-features/procedures/lambda-expressions.md)
