---
title: Procedimientos de Visual Basic | Microsoft Docs
ms.custom: 
ms.date: 2017-04-28
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- procedures, structured code
- Visual Basic code, procedures
- procedures, types of
- structured code, procedures
- procedures
ms.assetid: 9effbcf0-80a0-4d1a-98f4-2c6920592766
caps.latest.revision: 16
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d3f21e32c162133e70a124da125c30afc7303738
ms.openlocfilehash: 56f39e82e9295a9c1d9f862e3486373590a32e7f
ms.contentlocale: es-es
ms.lasthandoff: 05/15/2017

---
# <a name="procedures-in-visual-basic"></a>Procedimientos en Visual Basic
Un *procedimiento* es un bloque de instrucciones [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] incluido dentro de una instrucción de declaración (`Function`, `Sub`, `Operator`, `Get`, `Set`) y una declaración `End` coincidente. Todas las instrucciones ejecutables de [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] deben formar parte de algún procedimiento.  
  
## <a name="calling-a-procedure"></a>Llamada a un procedimiento  
 Cuando invoca un procedimiento desde otra parte del código, está realizando una *llamada a procedimiento*. Cuando el procedimiento termina de ejecutarse, devuelve el control al código que lo ha invocado, el cual se conoce como *código de llamada*. El código de llamada es una instrucción, o una expresión de una instrucción, que especifica el procedimiento por el nombre y le transfiere el control.  
  
## <a name="returning-from-a-procedure"></a>Devolución desde un procedimiento  
 Un procedimiento devuelve el control al código de llamada cuando termina de ejecutarse. Para ello, puede usar una [instrucción Return](../../../../visual-basic/language-reference/statements/return-statement.md), la [instrucción Exit](../../../../visual-basic/language-reference/statements/exit-statement.md) adecuada para el procedimiento o la instrucción [End \<keyword> Statement](../../../../visual-basic/language-reference/statements/end-keyword-statement.md) del procedimiento. A continuación, el control pasa al código de llamada seguido del punto de la llamada a procedimiento.  
  
-   Con una instrucción `Return`, el control vuelve inmediatamente al código de llamada. Las instrucciones que siguen la instrucción `Return` no se ejecutan. Puede tener más de una instrucción `Return` en el mismo procedimiento.  
  
-   Con una instrucción `Exit Sub` o `Exit Function`, el control vuelve inmediatamente al código de llamada. Las instrucciones siguientes a la instrucción `Exit` no se ejecutan. Puede tener más de una instrucción `Exit` en el mismo procedimiento. Además, puede combinar instrucciones `Return` y `Exit` en el mismo procedimiento.  
  
-   Si un procedimiento no tiene instrucciones `Return` o `Exit`, concluye con una instrucción `End Sub` o `End Function`, `End Get`, o `End Set` posterior a la última instrucción del cuerpo del procedimiento. La instrucción `End` devuelve inmediatamente el control al código de llamada. Solo puede tener una instrucción `End` en un procedimiento.  
  
## <a name="parameters-and-arguments"></a>Parámetros y argumentos  
 En la mayoría de los casos, un procedimiento necesita operar en datos diferentes cada vez que se llama. Puede pasar esta información al procedimiento como parte de la llamada a procedimiento. El procedimiento define cero o más *parámetros*, cada uno de los cuales representa un valor que espera que le pase. Cada parámetro de la definición del procedimiento tiene un *argumento* correspondiente en la llamada a procedimiento. Un argumento representa el valor que pasa al parámetro correspondiente en una llamada a procedimiento determinada.  
  
## <a name="types-of-procedures"></a>Tipos de procedimientos  
 [!INCLUDE[vbprvb](../../../../csharp/programming-guide/concepts/linq/includes/vbprvb_md.md)] usa varios tipos de procedimientos:  
  
-   Los [procedimientos Sub](./sub-procedures.md) realizan acciones, pero no devuelven un valor al código de llamada.  
  
-   Los procedimientos de control de eventos son procedimientos `Sub` que se ejecutan en respuesta a un evento debido a las acciones del usuario o a un incidente en un programa.  
  
-   Los [procedimientos Function](./function-procedures.md) devuelven un valor al código de llamada. Pueden realizar otras acciones antes de devolver el valor.

    Algunas funciones escritas en C# devuelven un *valor devuelto de referencia*. Los autores de llamadas a funciones pueden modificar el valor devuelto. Esta modificación se refleja en el estado del objeto al que se ha llamado. A partir de Visual Basic 2017, el código de Visual Basic puede consumir referencias de valores devueltos, aunque no puede devolver un valor por la referencia. Para obtener más información, consulte [Valores devueltos de referencia](ref-return-values.md).
  
-   Los [procedimientos Property](./property-procedures.md) devuelven y asignan valores de propiedades en objetos o módulos.  
  
-   Los [procedimientos Operator](./operator-procedures.md) definen el comportamiento de un operador estándar cuando uno de los operandos (o ambos) es una clase definida recientemente o una estructura.  
  
-   Los [procedimientos genéricos de Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md) definen uno o varios *parámetros de tipo* además de sus parámetros normales, por lo que el código de llamada puede pasar tipos de datos determinados cada vez que se hace una llamada.  
  
## <a name="procedures-and-structured-code"></a>Procedimientos y código estructurado  
 Cada línea de código ejecutable de la aplicación debe formar parte de algún procedimiento, como `Main`, `calculate` o `Button1_Click`. Si subdivide los procedimientos grandes en partes más pequeñas, la aplicación será más legible.  
  
 Los procedimientos son útiles para realizar tareas repetitivas o compartidas, como cálculos usados frecuentemente, la manipulación y el control de texto, o las operaciones de bases de datos. Puede llamar un procedimiento desde muchos lugares diferentes del código, por lo que puede usar los procedimientos como bloques de creación para la aplicación.  
  
 Estructurar el código con procedimientos le ofrece las ventajas siguientes:  
  
-   Los procedimientos permiten desglosar los programas en unidades lógicas discretas. Puede depurar unidades independientes más fácilmente que todo un programa sin procedimientos.  
  
-   Después de desarrollar procedimientos para su uso en un programa, se pueden usar en otros, a menudo con poca o ninguna modificación. Esto ayuda a evitar la duplicación de código.  
  
## <a name="see-also"></a>Consulte también  
 [Cómo: Crear un procedimiento](./how-to-create-a-procedure.md)   
 [Procedimientos Sub](./sub-procedures.md)   
 [Procedimientos Function](./function-procedures.md)   
 [Procedimientos Property](./property-procedures.md)   
 [Procedimientos Operator](./operator-procedures.md)   
 [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)   
 [Procedimientos Recursive](./recursive-procedures.md)   
 [Sobrecarga de procedimientos](./procedure-overloading.md)   
 [Procedimientos genéricos de Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-procedures.md)   
 [Objetos y clases](../../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
