---
title: Argumentos y parámetros de procedimiento (Visual Basic)
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
ms.openlocfilehash: b0ab186945b456d7fb4dde3f52724b08a99e2827
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="procedure-parameters-and-arguments-visual-basic"></a>Argumentos y parámetros de procedimiento (Visual Basic)
En la mayoría de los casos, un procedimiento necesita cierta información sobre las circunstancias en que se ha llamado. Un procedimiento que realiza las tareas repetitivas o compartidas utiliza información diferente para cada llamada. Esta información está formada por las variables, constantes y expresiones que se pasan al procedimiento cuando se llama al método.  
  
 A *parámetro* representa un valor que el procedimiento espera que se proporciona cuando se llama. La declaración del procedimiento define sus parámetros.  
  
 Puede definir un procedimiento sin parámetros, un parámetro o más de uno. La parte de la definición del procedimiento que especifica los parámetros se denomina la *lista de parámetros*.  
  
 Un *argumento* representa el valor que se proporciona a un parámetro de procedimiento cuando se llama al procedimiento. El código de llamada proporciona los argumentos cuando llama al procedimiento. La parte de la llamada del procedimiento que especifica los argumentos se denomina la *lista de argumentos*.  
  
 En la siguiente ilustración se muestra código que llama al procedimiento `safeSquareRoot` desde dos lugares diferentes. La primera llamada pasa el valor de la variable `x` (4.0) al parámetro `number`y el valor devuelto en `root` (2.0) se asigna a la variable `y`. La segunda llamada transfiere el valor literal 9.0 a `number`y asigna el valor devuelto (3.0) a la variable `z`.  
  
 ![Diagrama gráfico de paso de argumentos al parámetro](./media/parametersargue.gif "ParametersArgue")  
Pasar un argumento a un parámetro  
  
 Para obtener más información, consulte [diferencias entre parámetros y argumentos](./differences-between-parameters-and-arguments.md).  
  
## <a name="parameter-data-type"></a>Tipo de datos de parámetro  
 Definir un tipo de datos para un parámetro mediante el `As` cláusula en su declaración. Por ejemplo, la siguiente función acepta una cadena y un entero.  
  
 [!code-vb[VbVbcnProcedures#32](./codesnippet/VisualBasic/procedure-parameters-and-arguments_1.vb)]  
  
 Si la comprobación de tipos cambia ([Option Strict (instrucción)](../../../../visual-basic/language-reference/statements/option-strict-statement.md)) es `Off,` el `As` cláusula es opcional, salvo que si usa un parámetro, todos los parámetros deben utilizarlo. Si la comprobación de tipos es `On`, el `As` cláusula es obligatoria para todos los parámetros de procedimiento.  
  
 Si el código que realiza la llamada espera que proporcionar un argumento con un tipo de datos diferente del parámetro correspondiente, como `Byte` para un `String` parámetro, debe realizar una de las siguientes acciones:  
  
-   Proporcionar sólo argumentos con tipos de datos que se amplían al tipo de datos del parámetro;  
  
-   Establecer `Option Strict Off` para permitir que las conversiones de restricción implícitas; o  
  
-   Utilizar una palabra clave de conversión para convertir explícitamente el tipo de datos.  
  
### <a name="type-parameters"></a>Parámetros de tipo  
 A *procedimiento genérico* también define uno o más *parámetros de tipo* además de sus parámetros normales. Un procedimiento genérico permite que el código que realiza la llamada para pasar tipos de datos diferentes cada vez que llama al procedimiento, por lo que pueden personalizar los tipos de datos a los requisitos de cada llamada individual. Vea [Generic Procedures in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md).  
  
## <a name="see-also"></a>Vea también  
 [Procedimientos](./index.md)  
 [Subprocedimientos](./sub-procedures.md)  
 [Procedimientos de función](./function-procedures.md)  
 [Procedimientos de propiedades](./property-procedures.md)  
 [Procedimientos de operadores](./operator-procedures.md)  
 [Definir un parámetro para un procedimiento](./how-to-define-a-parameter-for-a-procedure.md)  
 [Pasar argumentos a un procedimiento](./how-to-pass-arguments-to-a-procedure.md)  
 [Paso de argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)  
 [Sobrecarga de procedimientos](./procedure-overloading.md)  
 [Conversiones de tipos en Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/type-conversions.md)
