---
title: Inferencia de tipo de variable local (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- local type inference
- vb.TypeInfer
helpviewer_keywords:
- Option Infer statement [Visual Basic]
- local type inference [Visual Basic]
- implicitly-typed local variables [Visual Basic]
- variables [Visual Basic], type inference
- inference [Visual Basic]
- type inference [Visual Basic]
ms.assetid: b8307f18-2e56-4ab3-a45a-826873f400f6
ms.openlocfilehash: e6214938262b987a1bae4a9ca1d5c945f8b7fe6e
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62052591"
---
# <a name="local-type-inference-visual-basic"></a>Inferencia de tipo de variable local (Visual Basic)
El compilador de Visual Basic usa *inferencia* para determinar los tipos de datos de variables locales declaradas sin un `As` cláusula. El compilador deduce el tipo de la variable del tipo de la expresión de inicialización. Esto le permite declarar variables sin especificar explícitamente un tipo, como se muestra en el ejemplo siguiente. Como resultado de las declaraciones, ambos `num1` y `num2` están fuertemente tipados como enteros.  
  
 [!code-vb[VbVbalrTypeInference#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#1)]  
 
> [!NOTE]
>  Si no desea `num2` en el ejemplo anterior a escribirse como un `Integer`, puede especificar otro tipo mediante el uso de una declaración como `Dim num3 As Object = 3` o `Dim num4 As Double = 3`.  

> [!NOTE]
>  Inferencia de tipo se puede usar solo para las variables locales de nestatické; no se puede utilizar para determinar el tipo de funciones, propiedades o campos de la clase.
 
 Inferencia de tipos local se aplica en el nivel de procedimiento. No se puede utilizar para declarar variables en el nivel de módulo (dentro de una clase, estructura, módulo o interfaz, pero no dentro de un procedimiento o bloque). Si `num2` en el ejemplo anterior eran un campo de una clase en lugar de una variable local en un procedimiento, la declaración provocaría un error con `Option Strict` y se pueden clasificar `num2` como un `Object` con `Option Strict` off. De forma similar, inferencia de tipo local no se aplica a las variables de nivel de procedimiento declaradas como `Static`.  
  
## <a name="type-inference-vs-late-binding"></a>Inferencia de tipos y Enlace en tiempo de ejecución  
 Código que usa la inferencia es similar al código que se basa en el enlace en tiempo de ejecución. Sin embargo, inferencia de tipos fuertemente la variable en lugar de dejarlo como `Object`. El compilador usa el inicializador de una variable para determinar el tipo de variable en tiempo de compilación para generar código de tiempo de compilación. En el ejemplo anterior, `num2`, como `num1`, se escribe como un `Integer`.  
  
 El comportamiento de las variables enlazadas tempranamente difiere de las variables en tiempo de ejecución, para el que se conoce el tipo en tiempo de ejecución. Conocer el tipo al principio, habilita el compilador identificar problemas antes de la ejecución, asignar memoria con precisión y realizar otras optimizaciones. Enlace anticipado también permite que el entorno de desarrollo integrado (IDE) para proporcionar IntelliSense ayuda acerca de los miembros de un objeto de Visual Basic. Enlace anticipado también es preferible para el rendimiento. Esto es porque se deben ajustar todos los datos almacenados en una variable en tiempo de ejecución como tipo `Object`, y obtener acceso a los miembros del tipo en tiempo de ejecución hace que el programa más lento.  
  
## <a name="examples"></a>Ejemplos  
 Inferencia de tipos se produce cuando se declara una variable local sin un `As` cláusula y se inicializa. El compilador utiliza el tipo del valor inicial asignado como el tipo de la variable. Por ejemplo, cada una de las siguientes líneas de código declara una variable de tipo `String`.  
  
 [!code-vb[VbVbalrTypeInference#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#2)]  
  
 El código siguiente muestra dos maneras equivalentes para crear una matriz de enteros.  
  
 [!code-vb[VbVbalrTypeInference#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#3)]  
  
 Es conveniente usar la inferencia de tipo para determinar el tipo de una variable de control de bucle. En el código siguiente, el compilador infiere que `number` es un `Integer` porque `someNumbers2` del ejemplo anterior es una matriz de enteros.  
  
 [!code-vb[VbVbalrTypeInference#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#4)]  
  
 Se puede usar la inferencia de tipos local en `Using` instrucciones para establecer el tipo del nombre del recurso, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrTypeInference#7](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#7)]  
  
 También se puede inferir el tipo de una variable de los valores devueltos de funciones, como se muestra en el ejemplo siguiente. Ambos `pList1` y `pList2` son matrices de procesos porque `Process.GetProcesses` devuelve una matriz de los procesos.  
  
 [!code-vb[VbVbalrTypeInference#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrTypeInference/VB/Class1.vb#5)]  
  
## <a name="option-infer"></a>Option Infer  
 `Option Infer` permite que especificar si se permite la inferencia de tipos local en un archivo determinado. Para habilitar o bloquear la opción, escriba una de las instrucciones siguientes al principio del archivo.  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 Si no especifica un valor para `Option Infer` en su código, es el valor predeterminado del compilador `Option Infer On`. Para actualizan proyectos desde [!INCLUDE[vb_orcas_long](~/includes/vb-orcas-long-md.md)] o versiones anteriores, es el valor predeterminado del compilador `Option Infer Off`.  
  
 Si el valor establecido para `Option Infer` en un archivo entra en conflicto con el valor establecido en el IDE o en la línea de comandos, el valor del archivo tiene prioridad.  
  
 Para obtener más información, consulte [instrucción Option Infer](../../../../visual-basic/language-reference/statements/option-infer-statement.md) y [página compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>Vea también

- [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
- [Enlace en tiempo de compilación y en tiempo de ejecución](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)
- [For Each...Next (instrucción)](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)
- [For...Next (instrucción)](../../../../visual-basic/language-reference/statements/for-next-statement.md)
- [Option Infer (instrucción)](../../../../visual-basic/language-reference/statements/option-infer-statement.md)
- [/optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)
- [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
