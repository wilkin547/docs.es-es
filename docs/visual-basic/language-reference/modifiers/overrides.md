---
title: "Overrides (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "Overrides"
  - "vb.Overrides"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Overrides (palabra clave)"
  - "reemplazar"
  - "reemplazar, Overrides (palabra clave)"
  - "procedimientos, reemplazar"
  - "procedimientos, redefinir"
  - "propiedades [Visual Basic], reemplazar"
  - "propiedades [Visual Basic], redefinir"
ms.assetid: 9f5e6144-ce10-465e-842b-1a8f8760af90
caps.latest.revision: 18
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 18
---
# Overrides (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica que una propiedad o procedimiento invalida una propiedad o procedimiento del mismo nombre heredado de una clase base.  
  
## Comentarios  
  
## Reglas  
  
-   **Contexto de declaración**. Puede usar `Overrides` únicamente en una instrucción de declaración de procedimiento o propiedad.  
  
-   **Modificadores combinados**. No es posible especificar `Overrides` junto con `Shadows` o `Shared` en la misma declaración.  Dado que un elemento de reemplazo es reemplazable de forma implícita, no se puede combinar `Overridable` con `Overrides`.  
  
-   **Firmas coincidentes**. La firma de esta declaración debe coincidir de forma exacta con la *firma* de la propiedad o el procedimiento al que reemplaza.  Esto significa que las listas de parámetros deben tener el mismo número de parámetros, en el mismo orden y con los mismos tipos de datos.  
  
     Además de coincidir con la firma, la declaración de reemplazo también debe coincidir de forma exacta con los elementos siguientes:  
  
    -   El nivel de acceso.  
  
    -   El tipo de valor devuelto, si lo hay.  
  
-   **Firmas genéricas**. En los procedimientos genéricos, la firma incluye el número de parámetros de tipo.  Por lo tanto, la declaración de reemplazo también debe coincidir con la versión de la clase base en este sentido.  
  
-   **Coincidencia adicional**. Además de coincidir con la firma de la versión de la clase base, esta declaración también debe coincidir con los elementos siguientes:  
  
    -   Modificador de nivel de acceso \(como [Public](../../../visual-basic/language-reference/modifiers/public.md)\).  
  
    -   Mecanismo de paso de cada parámetro \([ByVal](../../../visual-basic/language-reference/modifiers/byval.md) o [ByRef](../../../visual-basic/language-reference/modifiers/byref.md)\).  
  
    -   Listas de restricciones de los distintos parámetros de tipo de los procedimientos genéricos.  
  
-   **Sombreado y reemplazos**. Aunque tanto el sombreado como el reemplazo redefinen elementos heredados, existen diferencias significativas entre ambos conceptos.  Para obtener más información, consulte [Sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md).  
  
 Si usa `Overrides`, el compilador agregará `Overloads` de forma implícita para que las API de biblioteca trabajen con C\# más fácilmente.  
  
 El modificador `Overrides` se puede utilizar en los contextos siguientes:  
  
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)  
  
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)  
  
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)  
  
## Vea también  
 [MustOverride](../../../visual-basic/language-reference/modifiers/mustoverride.md)   
 [NotOverridable](../../../visual-basic/language-reference/modifiers/notoverridable.md)   
 [Overridable](../../../visual-basic/language-reference/modifiers/overridable.md)   
 [Palabras clave](../../../visual-basic/language-reference/keywords/index.md)   
 [Sombrear en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)   
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md)