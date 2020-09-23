---
title: Parámetros opcionales
ms.date: 07/20/2015
helpviewer_keywords:
- parameters [Visual Basic], optional
- Visual Basic code, procedures
- procedures [Visual Basic], optional arguments
- optional arguments
- named arguments [Visual Basic], and optional arguments
- optional parameters
- Optional keyword [Visual Basic], optional arguments
- arguments [Visual Basic], optional
- optional arguments [Visual Basic], and named arguments
ms.assetid: 398d2845-1069-4e94-b934-a73b545c8b87
ms.openlocfilehash: 73a51ab65a8ea4c38b6fd6737279fb19fb1cfe73
ms.sourcegitcommit: bf5c5850654187705bc94cc40ebfb62fe346ab02
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/23/2020
ms.locfileid: "91071864"
---
# <a name="optional-parameters-visual-basic"></a>Parámetros opcionales (Visual Basic)

Un parámetro de un procedimiento puede ser opcional si así se especifica y no es necesario proporcionarle argumentos al llamar al procedimiento. Los *parámetros opcionales* se indican mediante la `Optional` palabra clave en la definición del procedimiento. Se aplican las reglas siguientes:  
  
- Todos los parámetros opcionales de la definición del procedimiento deben especificar un valor predeterminado.  
  
- El valor predeterminado de un parámetro opcional debe ser una expresión constante.  
  
- Todos los parámetros que vayan a continuación de un parámetro opcional en la definición del procedimiento también deben ser opcionales.  
  
 La siguiente sintaxis muestra una declaración de procedimiento con un parámetro opcional:  
  
```vb  
Sub name(ByVal parameter1 As datatype1, Optional ByVal parameter2 As datatype2 = defaultvalue)  
```  
  
## <a name="calling-procedures-with-optional-parameters"></a>Llamar a procedimientos con parámetros opcionales  

 Cuando se llama a un procedimiento con un parámetro opcional, se puede elegir si se proporciona o no el argumento. Si no se proporciona, el procedimiento utiliza el valor predeterminado declarado para dicho parámetro.  
  
 Si se omiten uno o más argumentos opcionales de la lista de argumentos, hay que utilizar comas sucesivas para delimitar sus posiciones. En el ejemplo de llamada siguiente se suministran los argumentos primero y cuarto, pero no el segundo ni el tercero:  
  
```vb  
Sub name(argument 1, , , argument 4)  
```  
  
 En el ejemplo siguiente se realizan algunas llamadas a la función `MsgBox`. `MsgBox` tiene un parámetro obligatorio y dos parámetros opcionales.  
  
 La primera llamada a `MsgBox` proporciona los tres argumentos en el orden en que `MsgBox` los define. La segunda llamada únicamente proporciona el argumento obligatorio. La tercera y la cuarta llamada proporcionan el primer y el tercer argumento. La tercera llamada lo hace por posición y la llamada cuarta, por nombre.  
  
 [!code-vb[VbVbcnProcedures#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#47)]  
  
## <a name="determining-whether-an-optional-argument-is-present"></a>Determinar si un argumento opcional está presente  

 En tiempo de ejecución un procedimiento no puede detectar si un argumento determinado se ha omitido o si el código de llamada ha suministrado de forma explícita el valor predeterminado de dicho argumento. Si fuese necesario hacer esta distinción, se podría establecer como valor predeterminado un valor improbable. En el procedimiento siguiente se define el parámetro opcional `office` y se prueba su valor predeterminado, `QJZ` , para ver si se ha omitido en la llamada:  
  
 [!code-vb[VbVbcnProcedures#46](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#46)]  
  
 Si el parámetro opcional es un tipo de referencia, como `String`, puede utilizar `Nothing` como valor predeterminado, siempre y cuando éste no sea un valor esperado para el argumento.  
  
## <a name="optional-parameters-and-overloading"></a>Parámetros opcionales y sobrecarga  

 Otra forma de definir un procedimiento con parámetros opcionales consiste en utilizar una sobrecarga. Si tiene un parámetro opcional, puede definir dos versiones sobrecargadas del procedimiento, una que acepte el parámetro y otra sin él. Este planteamiento se complica a medida que aumenta el número de parámetros opcionales. No obstante, tiene la ventaja de que permite saber con total certeza si el programa de llamada ha suministrado o no cada argumento opcional.  
  
## <a name="see-also"></a>Vea también

- [Procedimientos](./index.md)
- [Argumentos y parámetros de procedimiento](./procedure-parameters-and-arguments.md)
- [Pasar argumentos por valor y por referencia](./passing-arguments-by-value-and-by-reference.md)
- [Paso de argumentos por posición o por nombre](./passing-arguments-by-position-and-by-name.md)
- [Matrices de parámetros](./parameter-arrays.md)
- [Sobrecarga de procedimientos](./procedure-overloading.md)
- [Opcional](../../../language-reference/modifiers/optional.md)
- [ParamArray](../../../language-reference/modifiers/paramarray.md)
