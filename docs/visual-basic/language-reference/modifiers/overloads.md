---
title: Overloads (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.Overloads
- Overloads
helpviewer_keywords:
- Overloads keyword [Visual Basic]
- hiding by signature
- Shadows keyword [Visual Basic]
- signature, hiding by
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
ms.openlocfilehash: 0d68846938aba809a7a3a6f7d27f185bb90a39cb
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61920684"
---
# <a name="overloads-visual-basic"></a>Overloads (Visual Basic)
Especifica que una propiedad o procedimiento vuelve a declarar una o varias propiedades o procedimientos existentes con el mismo nombre.  
  
## <a name="remarks"></a>Comentarios  
 *Sobrecarga* es la práctica de proporcionar más de una definición para un nombre de propiedad o procedimiento dado en el mismo ámbito. Si vuelve a declarar una propiedad o procedimiento con una firma diferente a veces se denomina *ocultar mediante signatura*.  
  
## <a name="rules"></a>Reglas  
  
-   **Contexto de declaración.** Puede usar `Overloads` únicamente en una instrucción de declaración de procedimiento o propiedad.  
  
-   **Modificadores combinados.** No puede especificar `Overloads` junto con [sombras](../../../visual-basic/language-reference/modifiers/shadows.md) en la misma declaración de procedimiento.  
  
-   **Diferencias requeridas.** El *firma* en esta declaración debe ser diferente de la firma de cada propiedad o procedimiento que sobrecarga. La firma incluye el nombre de propiedad o procedimiento más lo siguiente:  
  
    -   el número de parámetros  
  
    -   el orden de los parámetros  
  
    -   los tipos de datos de los parámetros  
  
    -   el número de parámetros de tipo (para un procedimiento genérico)  
  
    -   el tipo de valor devuelto (solo para un procedimiento de operador de conversión)  
  
     Todas las sobrecargas deben tener el mismo nombre, pero cada una debe diferir de todas las demás en uno o varios de los aspectos anteriores. Esto permite al compilador distinguir qué versión debe utilizar cuando el código llama a la propiedad o el procedimiento.  
  
-   **Diferencias de no permitidas.** El cambio de uno o varios de los siguientes aspectos no es válido para sobrecargar una propiedad o un procedimiento, porque no forman parte de la firma:  
  
    -   si devuelve o no un valor (para un procedimiento)  
  
    -   el tipo de datos del valor devuelto (excepto para un operador de conversión)  
  
    -   los nombres de los parámetros o parámetros de tipo  
  
    -   las restricciones en los parámetros de tipo (para un procedimiento genérico)  
  
    -   palabras clave de modificador de parámetro (como `ByRef` o `Optional`)  
  
    -   palabras clave de modificador de propiedad o procedimiento (como `Public` o `Shared`)  
  
-   **Modificador opcional.** No es necesario usar el modificador `Overloads` al definir varias propiedades o procedimientos sobrecargados en la misma clase. Sin embargo, si utiliza `Overloads` en una de las declaraciones, debe utilizarlo en todas ellas.  
  
-   **Sombreado y sobrecarga.** `Overloads` También puede utilizarse para sombrear un miembro existente o un conjunto de miembros sobrecargados, en una clase base. Al utilizar `Overloads` de esta forma, declara la propiedad o el método con el mismo nombre y la misma lista de parámetros que el miembro de clase base y no proporciona la palabra clave `Shadows`.  
  
 Si usa `Overrides`, el compilador agrega de forma implícita `Overloads` para que las API de la biblioteca trabajen más fácilmente con C#.  
  
 El modificador `Overloads` se puede utilizar en los contextos siguientes:  
  
 [Function (instrucción)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator (instrucción)](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub (instrucción)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## <a name="see-also"></a>Vea también

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Sobrecarga de procedimientos](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Procedimientos de operadores](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)
- [Cómo: Definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)
