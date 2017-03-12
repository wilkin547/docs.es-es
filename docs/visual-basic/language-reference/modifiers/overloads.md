---
title: "Overloads (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Overloads"
  - "Overloads"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "ocultar mediante signatura"
  - "Overloads (palabra clave)"
  - "Shadows (palabra clave)"
  - "signatura, ocultar mediante"
ms.assetid: 0c6820b8-25b2-4664-bc59-5ca93c99c042
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# Overloads (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica que una propiedad o procedimiento vuelve a declarar una o varias propiedades o procedimientos existentes con el mismo nombre.  
  
## Comentarios  
 *Sobrecarga* es la práctica de proporcionar más de una definición para un nombre de propiedad o procedimiento dado en el mismo ámbito.  Volver a declarar una propiedad o un procedimiento con otra firma se denomina a veces *ocultar mediante signatura*.  
  
## Reglas  
  
-   **Contexto de declaración**. Puede usar `Overloads` únicamente en una instrucción de declaración de procedimiento o propiedad.  
  
-   **Modificadores combinados**. No es posible especificar `Overloads` junto con [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) en la misma declaración de procedimiento.  
  
-   **Diferencias requeridas**. La *firma* de esta declaración debe ser diferente a la de cada propiedad o procedimiento que sobrecarga.  La firma incluye el nombre de propiedad o procedimiento más lo siguiente:  
  
    -   el número de parámetros  
  
    -   el orden de los parámetros  
  
    -   los tipos de datos de los parámetros  
  
    -   el número de parámetros de tipo \(para un procedimiento genérico\)  
  
    -   el tipo de valor devuelto \(solo para un procedimiento de operador de conversión\)  
  
     Todas las sobrecargas deben tener el mismo nombre, pero cada una debe diferir de todas las demás en uno o varios de los aspectos anteriores.  Esto permite al compilador distinguir qué versión debe utilizar cuando el código llama a la propiedad o el procedimiento.  
  
-   **Diferencias no permitidas**. El cambio de uno o varios de los siguientes aspectos no es válido para sobrecargar una propiedad o un procedimiento, porque no forman parte de la firma:  
  
    -   si devuelve o no un valor \(para un procedimiento\)  
  
    -   el tipo de datos del valor devuelto \(excepto para un operador de conversión\)  
  
    -   los nombres de los parámetros o parámetros de tipo  
  
    -   las restricciones en los parámetros de tipo \(para un procedimiento genérico\)  
  
    -   palabras clave de modificador de parámetro \(como `ByRef` o `Optional`\)  
  
    -   palabras clave de modificador de propiedad o procedimiento \(como `Public` o `Shared`\)  
  
-   **Modificador opcional**. No es necesario usar el modificador `Overloads` al definir varias propiedades o procedimientos sobrecargados en la misma clase.  Sin embargo, si utiliza `Overloads` en una de las declaraciones, debe utilizarlo en todas ellas.  
  
-   **Sombreado y sobrecarga**. `Overloads` también puede utilizarse para sombrear un miembro existente o un conjunto de miembros sobrecargados en una clase base.  Al utilizar `Overloads` de esta forma, declara la propiedad o el método con el mismo nombre y la misma lista de parámetros que el miembro de clase base y no proporciona la palabra clave `Shadows`.  
  
 Si usa `Overrides`, el compilador agrega de forma implícita `Overloads` para que las API de la biblioteca trabajen más fácilmente con C\#.  
  
 El modificador `Overloads` se puede utilizar en los siguientes contextos:  
  
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Operator \(Instrucción\)](../../../visual-basic/language-reference/statements/operator-statement.md)  
  
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Vea también  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Sobrecarga de procedimientos](../../../visual-basic/programming-guide/language-features/procedures/procedure-overloading.md)   
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Procedimientos de operador](../../../visual-basic/programming-guide/language-features/procedures/operator-procedures.md)   
 [Cómo: Definir un operador de conversión](../../../visual-basic/programming-guide/language-features/procedures/how-to-define-a-conversion-operator.md)