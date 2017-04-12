---
title: "Llamar a una propiedad o método mediante un nombre de cadena (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- passing operators
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls, strings
- methods [Visual Basic], calling with string names
- calling methods, string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
caps.latest.revision: 17
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
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: 87af2816ba42e2901c53bec5e9c19f34c676ed5c
ms.lasthandoff: 03/13/2017

---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a>Llamar a una propiedad o método mediante un nombre de cadena (Visual Basic)
En la mayoría de los casos, puede descubrir las propiedades y métodos de un objeto en tiempo de diseño y escribir código para controlarlos. Sin embargo, en algunos casos puede no conocer acerca de los métodos y propiedades de un objeto de antemano o simplemente puede querer flexibilidad de la habilitación de un usuario final que especifique propiedades o ejecute métodos en tiempo de ejecución.  
  
## <a name="callbyname-function"></a>CallByName (función)  
 Considere, por ejemplo, una aplicación cliente que evalúe expresiones escritas por el usuario pasando un operador a un componente COM. Suponga que está agregando constantemente funciones nuevas al componente que requiere operadores nuevos. Cuando se usa técnicas de acceso a objetos estándar, debe volver a compilar y distribuir la aplicación cliente antes de poder utilizar los operadores nuevos. Para evitar esto, puede utilizar el `CallByName` función para pasar los operadores nuevos como cadenas, sin modificar la aplicación.  
  
 El `CallByName` función le permite utilizar una cadena para especificar una propiedad o método en tiempo de ejecución. La firma para el `CallByName` función tiene el siguiente aspecto:  
  
 *Result* = `CallByName`(*Object*, *ProcedureName*, *CallType*, *Arguments*())  
  
 El primer argumento, *objeto*, toma el nombre del objeto que desea actuar. El *nombreProcedimiento* argumento toma una cadena que contiene el nombre del procedimiento que se debe invocar método o propiedad. El *CallType* argumento toma una constante que representa el tipo de procedimiento que debe invocarse: un método (`Microsoft.VisualBasic.CallType.Method`), una lectura de propiedad (`Microsoft.VisualBasic.CallType.Get`), o un conjunto de propiedades (`Microsoft.VisualBasic.CallType.Set`). El *argumentos* argumento, que es opcional, toma una matriz de tipo `Object` que contiene los argumentos para el procedimiento.  
  
 Puede usar `CallByName` con clases en la solución actual, pero que se suele utilizar para tener acceso a objetos COM o los objetos de [!INCLUDE[dnprdnshort](../../../../csharp/getting-started/includes/dnprdnshort_md.md)] ensamblados.  
  
 Supongamos que se agrega una referencia a un ensamblado que contiene una clase denominada `MathClass`, que tiene una nueva función denominada `SquareRoot`, como se muestra en el código siguiente:  
  
 [!code-vb[VbVbalrOOP nº&53;](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_1.vb)]  
  
 La aplicación podría utilizar controles de cuadro de texto al control de qué método se llamará y sus argumentos. Por ejemplo, si `TextBox1` contiene la expresión que se evalúa, y `TextBox2` es utilizado para escribir el nombre de la función, puede usar el siguiente código para invocar la `SquareRoot` (función) en la expresión `TextBox1`:  
  
 [!code-vb[VbVbalrOOP&#54;](../../../../visual-basic/misc/codesnippet/VisualBasic/calling-a-property-or-method-using-a-string-name_2.vb)]  
  
 Si escribe "64" en `TextBox1`, "SquareRoot" en `TextBox2`y, a continuación, llame a la `CallMath` procedimiento, la raíz cuadrada del número de `TextBox1` se evalúa. El código del ejemplo invoca la `SquareRoot` función (que toma una cadena que contiene la expresión que se evalúa como un argumento requerido) y devuelve "8" en `TextBox1` (la raíz cuadrada de 64). Por supuesto, si el usuario escribe una cadena no válida en `TextBox2`si la cadena contiene el nombre de una propiedad en lugar de un método, o si el método tiene un argumento necesario adicional, se produce un error de tiempo de ejecución. Tendrá que agregar código de control de errores sólido cuando use `CallByName` para anticipar estos errores u otros.  
  
> [!NOTE]
>  Mientras el `CallByName` función puede resultar útil en algunos casos, debe sopesar su utilidad frente a las implicaciones de rendimiento: uso `CallByName` invocar un procedimiento es ligeramente más lenta que una llamada en tiempo de ejecución. Si invoca una función que se llama repetidamente, como dentro de un bucle, `CallByName` puede tener un efecto grave en el rendimiento.  
  
## <a name="see-also"></a>Vea también  
 <xref:Microsoft.VisualBasic.Interaction.CallByName%2A></xref:Microsoft.VisualBasic.Interaction.CallByName%2A>   
 [Determinación del tipo de objeto](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
