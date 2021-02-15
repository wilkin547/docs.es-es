---
description: 'Más información sobre: parámetros y argumentos de procedimientos (Visual Basic)'
title: Argumentos y parámetros de procedimiento
ms.date: 07/20/2015
helpviewer_keywords:
- procedures [Visual Basic], arguments
- procedures [Visual Basic], argument lists
- values [Visual Basic], passing to procedures
- arguments [Visual Basic], passing
- procedures [Visual Basic], parameters
- Visual Basic code, argument lists
- Visual Basic code, procedures
- parameters [Visual Basic], Visual Basic procedures
- parameters [Visual Basic], lists
- arguments [Visual Basic], Visual Basic procedures
- arguments [Visual Basic], procedures
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- argument lists [Visual Basic]
- procedures [Visual Basic], parameter lists
ms.assetid: ff275aff-aa13-40df-bd4c-63486db8c1e9
ms.openlocfilehash: c2239c76450f503e74dbf5f191cd212e05d11600
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/14/2021
ms.locfileid: "100423165"
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a>Argumentos y parámetros de procedimiento (Visual Basic)

En la mayoría de los casos, un procedimiento necesita cierta información sobre las circunstancias en las que se ha llamado. Un procedimiento que realiza tareas repetidas o compartidas utiliza información diferente para cada llamada. Esta información se compone de variables, constantes y expresiones que se pasan al procedimiento cuando se llama.  
  
 Un *parámetro* representa un valor que el procedimiento espera que proporcione al llamarlo. La declaración del procedimiento define sus parámetros.  
  
 Puede definir un procedimiento sin parámetros, un parámetro o más de uno. La parte de la definición de procedimiento que especifica los parámetros se denomina *lista de parámetros*.  
  
 Un *argumento* representa el valor que se proporciona a un parámetro de procedimiento cuando se llama al procedimiento. El código de llamada proporciona los argumentos cuando llama al procedimiento. La parte de la llamada a procedimiento que especifica los argumentos se denomina *lista de argumentos*.  
  
 En la ilustración siguiente se muestra el código que llama al procedimiento `safeSquareRoot` desde dos lugares diferentes. La primera llamada pasa el valor de la variable `x` (4,0) al parámetro `number` y el valor devuelto en `root` (2,0) se asigna a la variable `y` . La segunda llamada pasa el valor literal 9,0 a `number` y asigna el valor devuelto (3,0) a la variable `z` .  
  
 ![Diagrama que muestra cómo pasar un argumento a un parámetro](./media/procedure-parameters-and-arguments/pass-argument-parameter.gif)  
  
 Para obtener más información, vea [diferencias entre parámetros y argumentos](./differences-between-parameters-and-arguments.md).  
  
## <a name="parameter-data-type"></a>Parámetro, tipo de datos  

 Para definir un tipo de datos para un parámetro, use la `As` cláusula en su declaración. Por ejemplo, la función siguiente acepta una cadena y un entero.  
  
 [!code-vb[VbVbcnProcedures#32](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#32)]  
  
 Si el modificador de comprobación de tipo ([Option Strict Statement](../../../language-reference/statements/option-strict-statement.md)) es `Off,` la `As` cláusula es opcional, salvo que si alguno de los parámetros lo usa, todos los parámetros deben utilizarla. Si la comprobación de tipos es `On` , la `As` cláusula es necesaria para todos los parámetros de procedimiento.  
  
 Si el código de llamada espera proporcionar un argumento con un tipo de datos diferente del parámetro correspondiente, como `Byte` un `String` parámetro, debe realizar una de las siguientes acciones:  
  
- Proporcione solo argumentos con tipos de datos que se amplíen al tipo de datos del parámetro;  
  
- `Option Strict Off`Se establece para permitir las conversiones de restricción implícitas; o  
  
- Use una palabra clave de conversión para convertir explícitamente el tipo de datos.  
  
### <a name="type-parameters"></a>Parámetros de tipo  

 Un *procedimiento genérico* también define uno o varios *parámetros de tipo* además de sus parámetros normales. Un procedimiento genérico permite al código de llamada pasar tipos de datos diferentes cada vez que llama al procedimiento, por lo que puede personalizar los tipos de datos según los requisitos de cada llamada individual. Vea [Generic Procedures in Visual Basic](../data-types/generic-procedures.md).  
  
## <a name="see-also"></a>Consulte también

- [Procedimientos](./index.md)
- [Procedimientos Sub](./sub-procedures.md)
- [Procedimientos de función](./function-procedures.md)
- [Procedimientos de propiedad](./property-procedures.md)
- [Procedimientos de operador](./operator-procedures.md)
- [Procedimiento para definir un parámetro para un procedimiento](./how-to-define-a-parameter-for-a-procedure.md)
- [Procedimiento para pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)
- [Pasar argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Conversiones de tipos en Visual Basic](../data-types/type-conversions.md)
