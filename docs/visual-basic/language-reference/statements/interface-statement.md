---
title: "Instrucci&#243;n Interface (Visual Basic) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vb.Interface"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "interface (instrucción) [Visual Basic]"
  - "interfaces, definición de interfaces"
ms.assetid: 8997af73-bda3-4f79-bd41-ca396b610260
caps.latest.revision: 26
caps.handback.revision: 26
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Instrucci&#243;n Interface (Visual Basic)
[!INCLUDE[vs2017banner](../../../csharp/includes/vs2017banner.md)]

Declara el nombre de una interfaz e introduce las definiciones de los miembros que incluye la interfaz.  
  
## Sintaxis  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] _  
Interface name [ ( Of typelist ) ]  
    [ Inherits interfacenames ]  
    [ [ modifiers ] Property membername ]  
    [ [ modifiers ] Function membername ]  
    [ [ modifiers ] Sub membername ]  
    [ [ modifiers ] Event membername ]  
    [ [ modifiers ] Interface membername ]  
    [ [ modifiers ] Class membername ]  
    [ [ modifiers ] Structure membername ]  
End Interface  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`attributelist`|Opcional.  Vea la [Lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Opcional.  Puede ser una de las siguientes:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Vea [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Opcional.  Vea [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`name`|Obligatorio.  Nombre de esta interfaz.  Vea [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Opcional.  Especifica que ésta es una interfaz genérica.|  
|`typelist`|Obligatorio si se utiliza la palabra clave [Of](../../../visual-basic/language-reference/statements/of-clause.md).  Lista de parámetros de tipo de esta interfaz.  Opcionalmente, cada parámetro de tipo se puede declarar como variant utilizando los modificadores genéricos `In` y `Out`.  Vea [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Opcional.  Indica que esta interfaz hereda los atributos y miembros de otra interfaz o interfaces.  Vea [Inherits \(Instrucción\)](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`interfacenames`|Es obligatorio si se utiliza la instrucción `Inherits`.  Nombres de las interfaces de las que deriva esta interfaz.|  
|`modifiers`|Opcional.  Modificadores adecuados para el miembro de interfaz que se está definiendo.|  
|`Property`|Opcional.  Define una propiedad que es un miembro de la interfaz.|  
|`Function`|Opcional.  Define un procedimiento `Function` que es un miembro de la interfaz.|  
|`Sub`|Opcional.  Define un procedimiento `Sub` que es un miembro de la interfaz.|  
|`Event`|Opcional.  Define un evento que es un miembro de la interfaz.|  
|`Interface`|Opcional.  Define una interfaz que está anidada dentro de esta interfaz.  La definición de interfaz anidada debe finalizar con una instrucción `End Interface`.|  
|`Class`|Opcional.  Define una clase que es un miembro de la interfaz.  La definición de clase miembro debe finalizar con una instrucción `End Class`.|  
|`Structure`|Opcional.  Define una estructura que es un miembro de la interfaz.  La definición de estructura miembro debe finalizar con una instrucción `End Structure`.|  
|`membername`|Obligatorio para cada propiedad, procedimiento, evento, interfaz, clase o estructura definidos como miembro de la interfaz.  Nombre del miembro.|  
|`End Interface`|Termina la definición de `Interface`.|  
  
## Comentarios  
 Una *interfaz* define un conjunto de miembros, como las propiedades y procedimientos, que pueden implementar las clases y estructuras.  La interfaz sólo define las firmas de los miembros y no sus mecanismos internos.  
  
 Una clase o estructura implementa la interfaz proporcionando código para cada miembro definido por la interfaz.  Finalmente, cuando la aplicación crea una instancia a partir de esa clase o estructura, existe un objeto y se ejecuta en memoria.  Para obtener más información, vea [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md) y [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md).  
  
 Solo se puede utilizar `Interface` en el nivel de espacio de nombres o de módulo.  Esto significa que el *contexto de la declaración* de una interfaz debe ser un archivo de código fuente, espacio de nombres, clase, estructura, módulo o interfaz y no puede ser un procedimiento ni un bloque.  Para obtener más información, vea [Contextos de declaración y niveles de acceso predeterminados](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Las interfaces tienen [Friend](../../../visual-basic/language-reference/modifiers/friend.md) como acceso predeterminado.  Puede ajustar sus niveles de acceso con los modificadores de acceso.  Para obtener más información, vea [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## Reglas  
  
-   **Anidar interfaces.** Puede definir una interfaz dentro de otra.  La interfaz exterior se denomina la *interfaz contenedora* y la interfaz interior se denomina *interfaz anidada*.  
  
-   **Declaración de miembros** Cuando se declara una propiedad o procedimiento como miembro de una interfaz, se está definiendo sólo la *firma* de esa propiedad o procedimiento.  Esto incluye el tipo de elemento \(propiedad o procedimiento\), sus parámetros y tipos de parámetro y su tipo de valor devuelto.  Por esta razón, la definición de miembro sólo utiliza una línea de código y las instrucciones de terminación como `End Function` o `End Property` no son válidas en las interfaces.  
  
     En cambio, cuando define una enumeración o estructura, o una clase o interfaz anidada, es necesario incluir sus miembros de datos.  
  
-   **Modificadores de miembros.** No se puede utilizar ningún modificador de acceso al definir miembros de módulo, ni se puede especificar [Shared](../../../visual-basic/language-reference/modifiers/shared.md) ni ningún modificador de procedimiento excepto [Overloads](../../../visual-basic/language-reference/modifiers/overloads.md).  Puede declarar cualquier miembro con [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) y puede utilizar [Default](../../../visual-basic/language-reference/modifiers/default.md) al definir una propiedad, así como [ReadOnly](../../../visual-basic/language-reference/modifiers/readonly.md) o [WriteOnly](../../../visual-basic/language-reference/modifiers/writeonly.md).  
  
-   **Herencia.** Si la interfaz utiliza [Inherits \(Instrucción\)](../../../visual-basic/language-reference/statements/inherits-statement.md), se pueden especificar una o más interfaces base.  Puede heredar de dos interfaces incluso si cada una define un miembro con el mismo nombre.  Si lo hace así, el código de implementación debe utilizar la calificación del nombre para especificar qué miembro se implementa.  
  
     Una interfaz no puede heredar de otra interfaz con un nivel de acceso más restrictivo.  Por ejemplo, una interfaz de tipo `Public` no puede heredar una interfaz de tipo `Friend`.  
  
     Una interfaz no puede heredar de una interfaz anidada en ella.  
  
-   **Implementación.** Cuando una clase utiliza la instrucción [Implements](../../../visual-basic/language-reference/statements/implements-clause.md) para implementar esta interfaz, debe implementar todos los miembros definidos dentro de la interfaz.  Además, cada firma incluida el código que implementa debe coincidir exactamente con la firma correspondiente definida en esta interfaz.  Sin embargo, el nombre del miembro del código que implementa no tiene por qué coincidir con el nombre de miembro definido en la interfaz.  
  
     Cuando una clase está implementando un procedimiento, no puede designar el procedimiento como `Shared`.  
  
-   **Propiedad Default.** Una interfaz puede especificar a lo sumo una propiedad como *propiedad predeterminada*, a la que se puede hacer referencia sin utilizar el nombre de propiedad.  Esta propiedad se especifica declarándola con el modificador [Default](../../../visual-basic/language-reference/modifiers/default.md).  
  
     Observe que esto significa que una interfaz sólo puede definir una propiedad predeterminada si no hereda ninguna.  
  
## Comportamiento  
  
-   **Nivel de acceso.** Todos los miembros de interfaz tienen implícitamente acceso [Public](../../../visual-basic/language-reference/modifiers/public.md).  No puede utilizar ningún modificador de acceso al definir un miembro.  Sin embargo, una clase que implementa la interfaz puede declarar un nivel de acceso para cada miembro implementado.  
  
     Si asigna una instancia de clase a una variable, el nivel de acceso de sus miembros puede depender de si el tipo de datos de la variable es el de la interfaz subyacente o el de la clase implementadora.  Esto se ilustra en el siguiente ejemplo:  
  
     [!code-vb[VbVbalrStatements#39](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_1.vb)]  
  
     Si tiene acceso a los miembros de clase a través de `varAsInterface`, todos ellos tienen acceso público.  Sin embargo, si tiene acceso a los miembros a través de `varAsClass`, el procedimiento `Sub` `doSomething` tiene acceso privado.  
  
-   **Ámbito.** Una interfaz está en ámbito a lo largo de su espacio de nombres, clase, estructura o módulo.  
  
     El ámbito de cada uno de los miembros de la interfaz es la interfaz completa.  
  
-   **Período de duración.** Una interfaz no tiene en sí misma un período de duración, ni tampoco sus miembros.  Cuando una clase implementa una interfaz y se crea un objeto como una instancia de esa clase, el objeto tiene un período de duración dentro de la aplicación en la que se está ejecutando.  Para obtener más información, vea el apartado sobre períodos de duración en [Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md).  
  
## Ejemplo  
 El ejemplo siguiente utiliza la instrucción `Interface` para definir una interfaz denominada `thisInterface`, que se debe implementar con una instrucción `Property` y una instrucción `Function`.  
  
 [!code-vb[VbVbalrStatements#40](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/interface-statement_2.vb)]  
  
 Observe que las instrucciones `Property` y `Function` no introducen el bloques que terminan con `End Property` y `End Function` dentro de la interfaz.  Una interfaz sólo define las firmas de sus miembros.  Los bloques `Property` y `Function` completos aparecen en las clases que implementan `thisInterface`.  
  
## Vea también  
 [Interfaces](../../../visual-basic/programming-guide/language-features/interfaces/index.md)   
 [Class \(Instrucción\)](../../../visual-basic/language-reference/statements/class-statement.md)   
 [Module \(Instrucción\)](../../../visual-basic/language-reference/statements/module-statement.md)   
 [Structure \(Instrucción\)](../../../visual-basic/language-reference/statements/structure-statement.md)   
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Function \(Instrucción\)](../../../visual-basic/language-reference/statements/function-statement.md)   
 [Sub \(Instrucción\)](../../../visual-basic/language-reference/statements/sub-statement.md)   
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Varianza en interfaces genéricas](../Topic/Variance%20in%20Generic%20Interfaces%20\(C%23%20and%20Visual%20Basic\).md)   
 [In](../../../visual-basic/language-reference/modifiers/in-generic-modifier.md)   
 [Out](../../../visual-basic/language-reference/modifiers/out-generic-modifier.md)