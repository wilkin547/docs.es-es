---
title: 'Cómo: Crear un procedimiento que devuelve un valor'
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], defining
- Visual Basic code, procedures
- procedures [Visual Basic], returning a value
ms.assetid: 8ee19f95-a9ef-4033-963b-d224dca207c4
ms.openlocfilehash: 218dbb52abc0100724d38d10be91ef24252d5226
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74349719"
---
# <a name="how-to-create-a-procedure-that-returns-a-value-visual-basic"></a>Cómo: Crear un procedimiento que devuelve un valor (Visual Basic)
El procedimiento `Function` se usa para devolver un valor al código de llamada.  
  
### <a name="to-create-a-procedure-that-returns-a-value"></a>Para crear un procedimiento que devuelve un valor  
  
1. Fuera de cualquier otro procedimiento, use una instrucción `Function`, seguida de una instrucción `End Function`.  
  
2. En la instrucción `Function`, siga la palabra clave `Function` con el nombre del procedimiento y, a continuación, la lista de parámetros entre paréntesis.  
  
3. Siga los paréntesis con una cláusula `As` para especificar el tipo de datos del valor devuelto.  
  
4. Coloque las instrucciones de código del procedimiento entre las instrucciones `Function` y `End Function`.  
  
5. Use una instrucción `Return` para devolver el valor al código de llamada.  
  
     En el procedimiento `Function` siguiente se calcula el lado más largo o la hipotenusa de un triángulo de la derecha, dados los valores de los otros dos lados.  
  
     [!code-vb[VbVbcnProcedures#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#1)]  
  
     En el ejemplo siguiente se muestra una llamada típica a `hypotenuse`.  
  
     [!code-vb[VbVbcnProcedures#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#6)]  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Subprocedimientos](./sub-procedures.md)
- [Procedimientos de propiedades](./property-procedures.md)
- [Procedimientos de operadores](./operator-procedures.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Function (instrucción)](../../../../visual-basic/language-reference/statements/function-statement.md)
- [Devolver un valor de un procedimiento](./how-to-return-a-value-from-a-procedure.md)
- [Llamar a un procedimiento que devuelve un valor](./how-to-call-a-procedure-that-returns-a-value.md)
