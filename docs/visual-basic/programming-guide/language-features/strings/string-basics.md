---
title: Fundamentos de cadenas en Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Like operator
- strings [Visual Basic], Visual Basic
- strings [Visual Basic], regular expressions
ms.assetid: 5674418d-f00d-4f72-9f98-d15897793350
ms.openlocfilehash: 7d2477070dce558aa932c822852ac8ac9c6721e4
ms.sourcegitcommit: 869b5832b667915ac4a5dd8c86b1109ed26b6c08
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2018
ms.locfileid: "39332680"
---
# <a name="string-basics-in-visual-basic"></a>Fundamentos de cadenas en Visual Basic
El tipo de datos de `String` representa una serie de caracteres (y cada uno de ellos representa a su vez una instancia del tipo de datos `Char`). Este tema presenta los conceptos básicos de las cadenas en Visual Basic.  
  
## <a name="string-variables"></a>Variables de cadena  
 A una instancia de una cadena se le puede asignar un valor literal que represente una serie de caracteres. Por ejemplo:  
  
 [!code-vb[VbVbalrStrings#63](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_1.vb)]  
  
 Una variable `String` también puede aceptar cualquier expresión que se evalúe como una cadena. A continuación se muestran algunos ejemplos:  
  
 [!code-vb[VbVbalrStrings#64](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_2.vb)]  
  
 Cualquier literal que se asigna a una variable `String` debe ir entre comillas (""). Esto significa que una comilla contenida en una cadena no se puede representar mediante una comilla. Por ejemplo, el código siguiente causa un error del compilador:  
  
 [!code-vb[VbVbalrStrings#65](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_3.vb)]  
  
 Este código provoca un error porque el compilador termina la cadena después de la segunda comilla, y el resto de la cadena se interpreta como código. Para solucionar este problema, Visual Basic interpreta dos comillas en un literal de cadena como una comilla en la cadena. En el ejemplo siguiente se muestra la forma correcta de incluir una comilla en una cadena:  
  
 [!code-vb[VbVbalrStrings#66](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_4.vb)]  
  
 En el ejemplo anterior, las dos comillas que preceden a la palabra `Look` se convierten en una comilla en la cadena. Las tres comillas al final de la línea representan una comilla en la cadena y un carácter de terminación de cadena.  
  
 Los literales de cadena pueden contener varias líneas:  
  
```vb  
Dim x = "hello  
world"  
```  
  
 La cadena resultante contiene secuencias de nueva línea que usó en el literal de cadena (vbcr, vbcrlf, etc.).  La solución anterior ya no es necesaria:  
  
```vb  
Dim x = <xml><![CDATA[Hello  
World]]></xml>.Value  
```  
  
## <a name="characters-in-strings"></a>Caracteres en cadenas  
 Una cadena puede considerarse como una serie de valores `Char` y el tipo `String` tiene funciones integradas que permiten realizar muchas manipulaciones en una cadena similares a las permitidas por las matrices. Como toda la matriz en [!INCLUDE[dnprdnshort](~/includes/dnprdnshort-md.md)], son matrices de base cero. Puede hacer referencia a un carácter específico de una cadena con la propiedad `Chars`, que proporciona una forma de acceso a un carácter mediante la posición en la que este aparece en la cadena. Por ejemplo:  
  
 [!code-vb[VbVbalrStrings#67](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_5.vb)]  
  
 En el ejemplo anterior, la propiedad `Chars` de la cadena devuelve el cuarto carácter de la cadena, que es `D`, y lo asigna a `myChar`. También puede obtener la longitud de una cadena concreta mediante la propiedad `Length`. Si necesita realizar varias manipulaciones de tipo de matriz en una cadena, puede convertirla en una matriz de instancias de `Char` usando la función `ToCharArray` de la cadena. Por ejemplo:  
  
 [!code-vb[VbVbalrStrings#68](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_6.vb)]  
  
 La variable `myArray` contiene ahora una matriz de valores `Char` y cada uno representa un carácter de `myString`.  
  
## <a name="the-immutability-of-strings"></a>Inmutabilidad de cadenas  
 Una cadena es *inmutable*, lo que significa que su valor no puede cambiarse una vez que se ha creado. Sin embargo, esto no impide asignar más de un valor a una variable de cadena. Considere el ejemplo siguiente:  
  
 [!code-vb[VbVbalrStrings#69](../../../../visual-basic/language-reference/functions/codesnippet/VisualBasic/string-basics_7.vb)]  
  
 Aquí se crea una variable de cadena con un valor y, a continuación, se cambia su valor.   
  
 Más concretamente, en la primera línea, se crea una instancia de tipo `String` y se le asigna el valor `This string is immutable`. En la segunda línea del ejemplo se crea una nueva instancia y se le asigna el valor `Or is it?`, y la variable de cadena descarta su referencia a la primera instancia y almacena una referencia a la nueva instancia.  
  
 A diferencia de otros tipos de datos intrínsecos, `String` es un tipo de referencia. Cuando una variable de tipo de referencia se pasa como argumento a una función o subrutina, se pasa una referencia a la dirección de memoria donde se almacenan los datos en lugar del valor real de la cadena. Así, en el ejemplo anterior, el nombre de la variable sigue siendo el mismo, pero apunta a una nueva instancia diferente de la clase `String`, que contiene el nuevo valor.  
  
## <a name="see-also"></a>Vea también  
 [Introducción a las cadenas en Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)  
 [String (tipo de datos)](../../../../visual-basic/language-reference/data-types/string-data-type.md)  
 [Char (tipo de datos)](../../../../visual-basic/language-reference/data-types/char-data-type.md)  
 [Operaciones básicas de cadenas](../../../../standard/base-types/basic-string-operations.md)
