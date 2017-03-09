---
title: "Static (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Static"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "Static (palabra clave)"
  - "static (modificador)"
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
caps.latest.revision: 22
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 22
---
# Static (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Especifica si una o varias variables locales declaradas deben seguir existiendo y conservar sus últimos valores tras la finalización del procedimiento en el que se han declarado.  
  
## Comentarios  
 Normalmente, una variable local de un procedimiento deja de existir en cuanto finaliza el procedimiento.  Una variable estática sigue existiendo y conserva su valor más reciente.  La próxima vez que su código llame al procedimiento, no se reinicializa la variable y sigue conservando el último valor asignado.  Una variable estática sigue existiendo mientras dure la clase o módulo en donde está definida.  
  
## Reglas  
  
-   **Contexto de la declaración.** Sólo se puede utilizar `Static` en variables locales.  Esto significa que el contexto de la declaración para una variable `Static` debe ser un procedimiento o un bloque en un procedimiento y no puede ser un archivo de código fuente, un espacio de nombres, una clase, una estructura o un módulo.  
  
     No puede utilizar `Static` dentro de un procedimiento de estructura.  
  
-   No se pueden deducir los tipos de datos de las variables locales `Static`.  Para obtener más información, vea [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
-   **Modificadores combinados.** No se puede especificar `Static` junto con `ReadOnly`, `Shadows` o `Shared` en la misma declaración.  
  
## Comportamiento  
 Cuando se declara una variable estática en un procedimiento de `Shared` , sólo una copia de la variable estática está disponible para toda la aplicación.  Se llama a un procedimiento de `Shared` utilizando el nombre de clase, no una variable que apunta a una instancia de la clase.  
  
 Cuando se declara una variable estática en un procedimiento que no es `Shared`, sólo una copia de la variable disponible para cada instancia de la clase.  Se llama a un procedimiento no compartido mediante una variable que apunta a una instancia concreta de la clase.  
  
## Ejemplo  
 El siguiente ejemplo muestra el uso de `Static`.  
  
 [!code-vb[VbVbalrKeywords#5](../../../visual-basic/language-reference/codesnippet/visualbasic/static_1.vb)]  
  
 El valor `totalSales` de la variable `Static` únicamente se inicializa en 0 una vez.  Cada vez que se escribe `updateSales`, `totalSales` sigue teniendo el valor calculado más reciente.  
  
 El modificador `Static` se puede utilizar en este contexto:  
  
 [Dim \(Instrucción\)](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## Vea también  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)   
 [Shared](../../../visual-basic/language-reference/modifiers/shared.md)   
 [Período de duración en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)   
 [Declaración de variable](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)   
 [Estructuras](../../../visual-basic/programming-guide/language-features/data-types/structures.md)   
 [Inferencia de tipo de variable local](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)   
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)