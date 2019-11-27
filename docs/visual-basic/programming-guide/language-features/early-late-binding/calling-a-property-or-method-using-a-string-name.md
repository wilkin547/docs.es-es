---
title: Llamar a una propiedad o método mediante un nombre de cadena
ms.date: 07/20/2015
helpviewer_keywords:
- passing operators [Visual Basic]
- strings [Visual Basic], passing new operators as
- objects [Visual Basic], setting properties
- setting properties, object properties at run time
- method calls [Visual Basic], strings
- methods [Visual Basic], calling with string names
- calling methods [Visual Basic], string names
- properties [Visual Basic], setting at run time
- CallByName function
ms.assetid: 79a7b8b4-b8c7-4ad8-aca8-12a9a2b32f03
ms.openlocfilehash: cb584f0dfbd905ca071f9a86b1eab231f3017538
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74345206"
---
# <a name="calling-a-property-or-method-using-a-string-name-visual-basic"></a>Llamar a una propiedad o método mediante un nombre de cadena (Visual Basic)
En la mayoría de los casos, puede detectar las propiedades y los métodos de un objeto en tiempo de diseño y escribir código para controlarlos. Sin embargo, en algunos casos es posible que no conozca las propiedades y los métodos de un objeto de antemano, o que solo desee la flexibilidad de permitir que un usuario final especifique las propiedades o ejecute métodos en tiempo de ejecución.  
  
## <a name="callbyname-function"></a>Función CallByName  
 Considere, por ejemplo, una aplicación cliente que evalúa las expresiones especificadas por el usuario pasando un operador a un componente COM. Supongamos que va a agregar constantemente nuevas funciones al componente que requiere nuevos operadores. Cuando use técnicas de acceso a objetos estándar, debe volver a compilar y distribuir la aplicación cliente antes de poder utilizar los nuevos operadores. Para evitar esto, puede usar la función `CallByName` para pasar los operadores nuevos como cadenas, sin cambiar la aplicación.  
  
 La función `CallByName` permite usar una cadena para especificar una propiedad o un método en tiempo de ejecución. La firma de la función `CallByName` tiene el siguiente aspecto:  
  
 *Resultado* = `CallByName`(*Object*, *nombreprocedimiento*, *CallType*, *arguments*())  
  
 El primer argumento, *Object*, toma el nombre del objeto sobre el que desea actuar. El argumento *nombreprocedimiento* toma una cadena que contiene el nombre del método o el procedimiento de propiedad que se va a invocar. El argumento *CallType* toma una constante que representa el tipo de procedimiento que se va a invocar: un método (`Microsoft.VisualBasic.CallType.Method`), una propiedad read (`Microsoft.VisualBasic.CallType.Get`) o un conjunto de propiedades (`Microsoft.VisualBasic.CallType.Set`). El argumento *arguments* , que es opcional, toma una matriz de tipo `Object` que contiene argumentos para el procedimiento.  
  
 Puede usar `CallByName` con clases en la solución actual, pero se suele usar para tener acceso a objetos COM u objetos de .NET Framework ensamblados.  
  
 Supongamos que agrega una referencia a un ensamblado que contiene una clase denominada `MathClass`, que tiene una nueva función denominada `SquareRoot`, tal y como se muestra en el código siguiente:  
  
 [!code-vb[VbVbalrOOP#53](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#53)]  
  
 La aplicación podría usar controles de cuadro de texto para controlar el método al que se llamará y sus argumentos. Por ejemplo, si `TextBox1` contiene la expresión que se va a evaluar y `TextBox2` se usa para escribir el nombre de la función, puede usar el siguiente código para invocar la función `SquareRoot` en la expresión de `TextBox1`:  
  
 [!code-vb[VbVbalrOOP#54](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrOOP/VB/OOP.vb#54)]  
  
 Si escribe "64" en `TextBox1`, "SquareRoot" en `TextBox2`y, a continuación, llama al procedimiento `CallMath`, se evalúa la raíz cuadrada del número en `TextBox1`. El código del ejemplo invoca la función `SquareRoot` (que toma una cadena que contiene la expresión que se va a evaluar como argumento obligatorio) y devuelve "8" en `TextBox1` (la raíz cuadrada de 64). Por supuesto, si el usuario escribe una cadena no válida en `TextBox2`, si la cadena contiene el nombre de una propiedad en lugar de un método o si el método tenía un argumento necesario adicional, se produce un error en tiempo de ejecución. Tiene que agregar un código de control de errores sólido al usar `CallByName` para anticiparse a estos o a cualquier otro error.  
  
> [!NOTE]
> Aunque la función `CallByName` puede ser útil en algunos casos, debe sopesar su utilidad en cuanto a las implicaciones de rendimiento, el uso de `CallByName` para invocar un procedimiento es ligeramente más lento que una llamada enlazada en tiempo de ejecución. Si va a invocar una función a la que se llama repetidamente, como dentro de un bucle, `CallByName` puede tener un efecto grave en el rendimiento.  
  
## <a name="see-also"></a>Vea también

- <xref:Microsoft.VisualBasic.Interaction.CallByName%2A>
- [Determinación del tipo de objeto](../../../../visual-basic/programming-guide/language-features/early-late-binding/determining-object-type.md)
