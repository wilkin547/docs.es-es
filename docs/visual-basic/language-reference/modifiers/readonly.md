---
title: "ReadOnly (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.ReadOnly"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "propiedades [Visual Basic], solo lectura"
  - "ReadOnly (palabra clave)"
  - "ReadOnly (propiedad)"
  - "variables de solo lectura"
  - "variables [Visual Basic], solo lectura"
ms.assetid: e868185d-6142-4359-a2fd-a7965cadfce8
caps.latest.revision: 15
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 15
---
# ReadOnly (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica que una variable o una propiedad se puede leer, pero no se puede modificar.  
  
## Comentarios  
  
## Reglas  
  
-   **Contexto de la declaración.** Sólo puede utilizar `ReadOnly` en el nivel de módulo.  Esto significa que el contexto de declaración de un elemento `ReadOnly` debe ser una clase, una estructura o un módulo, y no un archivo de código fuente, un espacio de nombres o un procedimiento.  
  
-   **Modificadores combinados.** No se puede especificar `ReadOnly` junto con `Static` en la misma declaración.  
  
-   **Asignar un valor.** El código que utiliza una propiedad `ReadOnly` no puede establecer su valor.  Pero el código que tiene acceso al almacenamiento subyacente puede asignar o modificar el valor en cualquier momento.  
  
     Sólo puede asignar un valor a una variable `ReadOnly` en su declaración o en el constructor de una clase o estructura en la que está definida.  
  
## Cuándo utilizar una variable de sólo lectura  
 Hay situaciones en las que no puede utilizar [Const \(Instrucción\)](../../../visual-basic/language-reference/statements/const-statement.md) para declarar y asignar un valor constante.  Por ejemplo, podría ocurrir que la instrucción `Const` no aceptara el tipo de datos que desea asignar o que no pueda calcular el valor en tiempo de compilación con una expresión constante.  Es posible incluso que no conozca el valor en tiempo de compilación.  En estos casos, puede utilizar una variable `ReadOnly` para albergar un valor constante.  
  
> [!IMPORTANT]
>  Si el tipo de datos de la variable es un tipo de referencia, como una matriz o una instancia de clase, sus miembros se pueden modificar aunque la propia variable sea `ReadOnly`.  Esto se ilustra en el siguiente ejemplo:  
  
 `ReadOnly characterArray() As Char = {"x"c, "y"c, "z"c}`  
  
 `Sub changeArrayElement()`  
  
 `characterArray(1) = "M"c`  
  
 `End Sub`  
  
 Cuando se inicializa, la matriz señalada por `characterArray()` alberga "x", "y" y "z".  Como la variable `characterArray` es `ReadOnly`, no es posible modificar su valor una vez que se ha inicializado; es decir, no se le puede asignar una nueva matriz.  Sin embargo, puede cambiar los valores de uno o varios miembros de la matriz.  Después de que se produzca una llamada al procedimiento `changeArrayElement`, la matriz señalada por `characterArray()` alberga "x", "M" y "z".  
  
 Observe que esta operación es equivalente a declarar un parámetro de procedimiento que sea [ByVal](../../../visual-basic/language-reference/modifiers/byval.md), lo que impide que el procedimiento pueda modificar el argumento de llamada, aunque puede modificar sus miembros.  
  
## Ejemplo  
 En el ejemplo siguiente se define una propiedad `ReadOnly` para la fecha en la que se contrató a un empleado.  La clase almacena el valor de propiedad internamente como una variable `Private` y únicamente el código incluido en la clase puede cambiar ese valor.  Sin embargo, la propiedad es `Public` y cualquier código que pueda tener acceso a la clase podrá leer la propiedad.  
  
 [!code-vb[VbVbalrKeywords#4](../../../visual-basic/language-reference/codesnippet/VisualBasic/readonly_1.vb)]  
  
 El modificador `ReadOnly` se puede utilizar en estos contextos:  
  
 [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
## Vea también  
 [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md)   
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)