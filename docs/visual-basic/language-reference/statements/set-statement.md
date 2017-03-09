---
title: "Instrucci&#243;n Set (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Set"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "propiedades [Visual Basic], de solo escritura"
  - "procedimientos de propiedades, Set (instrucciones)"
  - "Set (instrucción)"
  - "Set (instrucción), sintaxis"
  - "propiedades de solo escritura"
ms.assetid: 9ecc27b4-df84-420d-9075-db25455fb3cd
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 16
---
# Instrucci&#243;n Set (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Declara un procedimiento de propiedad `Set` que se utiliza para asignar un valor a una propiedad.  
  
## Sintaxis  
  
```  
[ <attributelist> ] [ accessmodifier ] Set (ByVal value [ As datatype ])  
    [ statements ]  
End Set  
```  
  
## Elementos  
 `attributelist`  
 Opcional.  Vea la [Lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md).  
  
 `accessmodifier`  
 Opcional en un máximo de una de las instrucciones `Get` y `Set` de esta propiedad.  Puede ser una de las siguientes:  
  
-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)  
  
-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
  
-   [Private](../../../visual-basic/language-reference/modifiers/private.md)  
  
-   `Protected Friend`  
  
 Vea [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
 `value`  
 Obligatorio.  Parámetro que contiene el nuevo valor de la propiedad.  
  
 `datatype`  
 Obligatorio si `Option Strict` es `On`.  Tipo de datos del parámetro `value`.  El tipo de datos especificado debe ser el mismo que el tipo de datos de la propiedad donde se declara esta instrucción `Set`.  
  
 `statements`  
 Opcional.  Una o más instrucciones que se ejecutan cuando se llama al procedimiento de propiedad `Set`.  
  
 `End Set`  
 Obligatorio.  Termina la definición del procedimiento de propiedad `Set`.  
  
## Comentarios  
 Cada propiedad debe tener un procedimiento de propiedad `Set`, a menos que la propiedad se marque como `ReadOnly`.  El procedimiento `Set` se utiliza para establecer el valor de la propiedad.  
  
 Visual Basic llama automáticamente al procedimiento `Set` de una propiedad cuando una instrucción de asignación proporciona un valor que se va a almacenar en la propiedad.  
  
 Visual Basic pasa un parámetro al procedimiento `Set` durante las asignaciones de propiedades.  Si no se especifica un parámetro para `Set`, el entorno de desarrollo integrado \(IDE\) utiliza un parámetro implícito denominado `value`.  El parámetro contiene el valor que se va a asignar a la propiedad.  Generalmente, almacena este valor en una variable local privada y lo devuelve cada vez que se llama al procedimiento `Get`.  
  
 El cuerpo de la declaración de propiedad sólo puede contener los procedimientos `Get` y `Set` de la propiedad entre [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md) y `End Property` No puede almacenar nada distinto de esos procedimientos.  En particular, no puede almacenar el valor actual de la propiedad.  Este valor debe almacenarse fuera de la propiedad, ya que si lo almacena en uno de los procedimientos de la propiedad, el otro procedimiento no puede tener acceso a él.  El enfoque habitual consiste en almacenar el valor en una variable [Private](../../../visual-basic/language-reference/modifiers/private.md) declarada en el mismo nivel que la propiedad.  Debe definir un procedimiento `Set` dentro de la propiedad a la que se aplica.  
  
 El procedimiento `Set` tiene como valor predeterminado el nivel de acceso de su propiedad contenedora, a menos que utilice `accessmodifier` en la instrucción `Set`.  
  
## Reglas  
  
-   **Niveles mixtos de acceso.** Si define una propiedad de lectura y escritura, puede especificar opcionalmente un nivel de acceso diferente para el procedimiento `Get` o `Set`, pero no para ambos.  Si hace esto, el nivel de acceso del procedimiento debe ser más restrictivo que el nivel de acceso de la propiedad.  Por ejemplo, si la propiedad se declara como `Friend`, puede declarar el procedimiento `Set` como `Private`, pero no como `Public`.  
  
     Si define una propiedad `WriteOnly`, el procedimiento `Set` representa la propiedad completa.  No puede declarar un nivel de acceso diferente para `Set`, porque esto establecería dos niveles de acceso para la propiedad.  
  
## Comportamiento  
  
-   **Volver de un procedimiento de propiedad.** Cuando el procedimiento `Set` vuelve al código de llamada, la ejecución continúa a partir de la instrucción que proporcionó el valor que se va a almacenar.  
  
     Los procedimientos de propiedad `Set` pueden volver utilizando [Return \(Instrucción\)](../../../visual-basic/language-reference/statements/return-statement.md) o [Exit \(Instrucción\)](../../../visual-basic/language-reference/statements/exit-statement.md).  
  
     Las instrucciones `Exit Property` y `Return` provocan una salida inmediata de un procedimiento de propiedad.  Puede aparecer cualquier número de instrucciones `Exit Property` y `Return` en cualquier parte del procedimiento y puede combinar instrucciones `Exit Property` y `Return`.  
  
## Ejemplo  
 En el siguiente ejemplo se utiliza la instrucción `Set` para establecer el valor de una propiedad.  
  
 [!code-vb[VbVbalrStatements#55](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/set-statement_1.vb)]  
  
## Vea también  
 [Get \(Instrucción\)](../../../visual-basic/language-reference/statements/get-statement.md)   
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Procedimientos de propiedad](../../../visual-basic/programming-guide/language-features/procedures/property-procedures.md)