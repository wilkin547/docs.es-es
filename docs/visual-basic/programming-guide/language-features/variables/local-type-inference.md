---
title: Inferencia de tipo de variable local (Visual Basic)
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: "43"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d753d1fbdc60f70dcf0513d809f28a112243c111
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="local-type-inference-visual-basic"></a>Inferencia de tipo de variable local (Visual Basic)
El compilador de Visual Basic utiliza *inferencia de tipo* para determinar los tipos de datos de variable local declarada sin una `As` cláusula. El compilador deduce el tipo de la variable del tipo de la expresión de inicialización. Esto permite declarar variables sin especificar explícitamente un tipo, como se muestra en el ejemplo siguiente. Como resultado de las declaraciones, ambos `num1` y `num2` están fuertemente tipados como enteros.  
  
 [!code-vb[VbVbalrTypeInference#1](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_1.vb)]  
 
> [!NOTE]
>  Si no desea `num2` en el ejemplo anterior a escribirse como un `Integer`, puede especificar otro tipo mediante una declaración como `Dim num3 As Object = 3` o `Dim num4 As Double = 3`.  

> [!NOTE]
>  Inferencia de tipo puede usarse solo para las variables locales de no estáticos; no podría usarse para determinar el tipo de funciones, propiedades o campos de la clase.
 
 Inferencia de tipo local se aplica en el nivel de procedimiento. No se puede utilizar para declarar variables en el nivel de módulo (dentro de una clase, estructura, módulo o interfaz, pero no dentro de un procedimiento o bloque). Si `num2` en el ejemplo anterior fuera un campo de una clase en lugar de una variable local en un procedimiento, la declaración provocaría un error con `Option Strict` y se pueden clasificar `num2` como un `Object` con `Option Strict` off. De forma similar, inferencia de tipo local no se aplica a las variables de nivel de procedimiento declaradas como `Static`.  
  
## <a name="type-inference-vs-late-binding"></a>Inferencia de tipos y Enlace tardío  
 Código que usa la inferencia de tipo es similar al código que se basa en el enlace más tarde. Sin embargo, la inferencia de tipo fuertemente tipos la variable en lugar de dejarlo como `Object`. El compilador utiliza el inicializador de una variable para determinar el tipo de la variable en tiempo de compilación para generar código de tiempo de compilación. En el ejemplo anterior, `num2`, como `num1`, se escribe como un `Integer`.  
  
 El comportamiento de las variables enlazadas tempranamente difiere de las variables en tiempo de ejecución, para el que se conoce el tipo en tiempo de ejecución. Conocer el tipo de una fase temprana permite al compilador identificar problemas antes de la ejecución, asignar memoria con precisión y realice otras optimizaciones. Enlace temprano también permite que el entorno de desarrollo integrado (IDE) para proporcionar ayuda de IntelliSense sobre los miembros de un objeto de Visual Basic. Enlace temprano también es preferible para el rendimiento. Esto es porque todos los datos almacenados en una variable en tiempo de ejecución se deben ajustar como tipo `Object`, y obtener acceso a miembros del tipo en tiempo de ejecución se convierte en el programa más lento.  
  
## <a name="examples"></a>Ejemplos  
 Inferencia de tipo se produce cuando se declara una variable local sin un `As` cláusula e inicializado. El compilador utiliza el tipo del valor inicial asignado como el tipo de la variable. Por ejemplo, cada una de las siguientes líneas de código declara una variable de tipo `String`.  
  
 [!code-vb[VbVbalrTypeInference#2](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_2.vb)]  
  
 El código siguiente muestra dos maneras equivalentes para crear una matriz de enteros.  
  
 [!code-vb[VbVbalrTypeInference#3](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_3.vb)]  
  
 Es conveniente usar la inferencia de tipo para determinar el tipo de una variable de control de bucle. En el código siguiente, el compilador deduce que `number` es un `Integer` porque `someNumbers2` del ejemplo anterior es una matriz de enteros.  
  
 [!code-vb[VbVbalrTypeInference#4](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_4.vb)]  
  
 Inferencia de tipo local puede utilizarse en `Using` instrucciones para establecer el tipo del nombre del recurso, como se muestra en el ejemplo siguiente.  
  
 [!code-vb[VbVbalrTypeInference#7](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_5.vb)]  
  
 El tipo de una variable también puede deducirse de los valores devueltos de funciones, como se muestra en el ejemplo siguiente. Ambos `pList1` y `pList2` son matrices de procesos porque `Process.GetProcesses` devuelve una matriz de procesos.  
  
 [!code-vb[VbVbalrTypeInference#5](../../../../visual-basic/language-reference/statements/codesnippet/VisualBasic/local-type-inference_6.vb)]  
  
## <a name="option-infer"></a>Option Infer  
 `Option Infer`permite que especificar si se permite la inferencia de tipo local en un archivo determinado. Para permitir o bloquear la opción, escriba una de las siguientes instrucciones al principio del archivo.  
  
 `Option Infer On`  
  
 `Option Infer Off`  
  
 Si no especifica un valor para `Option Infer` en el código, es el valor predeterminado del compilador `Option Infer On`. Para los proyectos actualizan desde [!INCLUDE[vb_orcas_long](~/includes/vb-orcas-long-md.md)] o versiones anteriores, el valor predeterminado del compilador es `Option Infer Off`.  
  
 Si el valor establecido para `Option Infer` en un archivo entra en conflicto con el valor establecido en el IDE o en la línea de comandos, el valor del archivo tiene prioridad.  
  
 Para obtener más información, consulte [Option Infer instrucción](../../../../visual-basic/language-reference/statements/option-infer-statement.md) y [página compilación, Diseñador de proyectos (Visual Basic)](/visualstudio/ide/reference/compile-page-project-designer-visual-basic).  
  
## <a name="see-also"></a>Vea también  
 [Tipos anónimos](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)  
 [Enlace en tiempo de compilación y en tiempo de ejecución](../../../../visual-basic/programming-guide/language-features/early-late-binding/index.md)  
 [For Each...Next (instrucción)](../../../../visual-basic/language-reference/statements/for-each-next-statement.md)  
 [For...Next (instrucción)](../../../../visual-basic/language-reference/statements/for-next-statement.md)  
 [Option Infer (instrucción)](../../../../visual-basic/language-reference/statements/option-infer-statement.md)  
 [/optioninfer](../../../../visual-basic/reference/command-line-compiler/optioninfer.md)  
 [Introducción a LINQ en Visual Basic](../../../../visual-basic/programming-guide/language-features/linq/introduction-to-linq.md)
