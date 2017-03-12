---
title: "Instrucci&#243;n Class (Visual Basic) | Microsoft Docs"
ms.date: "2015-07-20"
ms.prod: ".net"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.topic: "article"
f1_keywords: 
  - "vb.Class"
dev_langs: 
  - "VB"
helpviewer_keywords: 
  - "módulos de clase"
  - "Class (instrucción)"
  - "tipos de clase, Class (instrucciones)"
  - "clases [Visual Basic], crear"
  - "clases [Visual Basic], miembros de datos"
  - "clases [Visual Basic], campos"
  - "miembros de datos, de clases"
  - "campos, de clases"
ms.assetid: f2664f38-eb5a-4d4b-a374-1d041521fb6c
caps.latest.revision: 29
author: "stevehoag"
ms.author: "shoag"
caps.handback.revision: 29
---
# Instrucci&#243;n Class (Visual Basic)
[!INCLUDE[vs2017banner](../../../visual-basic/developing-apps/includes/vs2017banner.md)]

Declara el nombre de una clase e introduce la definición de las variables, propiedades, eventos y procedimientos que la clase comprende.  
  
## Sintaxis  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] [ Partial ] _  
Class name [ ( Of typelist ) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ statements ]  
End Class  
```  
  
## Elementos  
  
|||  
|-|-|  
|Término|Definición|  
|`attributelist`|Opcional.  Vea la [Lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Opcional.  Puede ser una de las siguientes:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protected](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Private](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Vea [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Opcional.  Vea [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Opcional.  Vea [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Opcional.  Vea [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`Partial`|Opcional.  Indica una definición parcial de la clase.  Vea [Partial](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Obligatorio.  Nombre de la clase.  Vea [Nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Opcional.  Especifica que ésta es una clase genérica.|  
|`typelist`|Es obligatorio si se utiliza la palabra clave [Of](../../../visual-basic/language-reference/statements/of-clause.md).  Lista de parámetros de tipo de la clase.  Vea [Lista de tipos](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Opcional.  Indica que esta clase hereda los miembros de otra clase.  Vea [Inherits \(Instrucción\)](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Es obligatorio si se utiliza la instrucción `Inherits`.  Nombre de la clase de la que se deriva esta clase.|  
|`Implements`|Opcional.  Indica que la clase implementa los miembros de una o más interfaces.  Vea [Implements \(Instrucción\)](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Es obligatorio si se utiliza la instrucción `Implements`.  Nombres de las interfaces implementadas por esta clase.|  
|`statements`|Opcional.  Instrucciones que definen los miembros de la clase.|  
|`End Class`|Obligatorio.  Finaliza la definición de `Class`.|  
  
## Comentarios  
 Una instrucción `Class` define un nuevo tipo de datos.  Una *clase* es un bloque de creación fundamental de la programación orientada a objetos \(OOP\).  Para obtener más información, vea [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
 Solo se puede utilizar `Class` en el nivel de espacio de nombres o de módulo.  Esto significa que el *contexto de declaración* para una clase debe ser un archivo de código fuente, espacio de nombres, clase, estructura, módulo o interfaz, y no puede ser un procedimiento o bloque.  Para obtener más información, vea [Contextos de declaración y niveles de acceso predeterminados](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md).  
  
 Cada instancia de una clase tiene un período de duración independiente de todas las demás instancias.  Este período de duración comienza cuando una cláusula [New \(Operador\)](../../../visual-basic/language-reference/operators/new-operator.md) o una función como <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A> crean la instancia.  Finaliza cuando todas las variables que señalan a la instancia se han establecido como [Nothing](../../../visual-basic/language-reference/nothing.md) o como instancias de otras clases.  
  
 Las clases tienen el acceso [Friend](../../../visual-basic/language-reference/modifiers/friend.md) de forma predeterminada.  Puede ajustar sus niveles de acceso con los modificadores de acceso.  Para obtener más información, vea [Niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## Reglas  
  
-   **Anidación.** Se puede definir una clase dentro de otra.  La clase exterior se denomina *clase contenedora* y la clase interna se denomina *clase anidada*.  
  
-   **Herencia.** Si la clase utiliza [Inherits \(Instrucción\)](../../../visual-basic/language-reference/statements/inherits-statement.md), solo se puede especificar una clase base o interfaz.  Una clase no puede heredar de más de un elemento.  
  
     Una clase no puede heredar de otra clase que tenga un nivel de acceso más restrictivo.  Por ejemplo, una clase `Public` no puede heredar de una clase `Friend`.  
  
     Una clase no puede heredar de una clase anidada dentro de ella.  
  
-   **Implementación.** Si la clase utiliza [Implements \(Instrucción\)](../../../visual-basic/language-reference/statements/implements-statement.md), se debe implementar cada miembro definido por cada interfaz que se especifique en `interfacenames`.  Una excepción a esto es la reimplementación de un miembro de clase base.  Para obtener más información, vea "Reimplementación" en [Implements](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
-   **Propiedad Default.** Una clase puede especificar a lo sumo una propiedad como su *propiedad predeterminada*.  Para obtener más información, vea [Default](../../../visual-basic/language-reference/modifiers/default.md).  
  
## Comportamiento  
  
-   **Nivel de acceso.** Dentro de una clase, se puede declarar cada miembro con su propio nivel de acceso.  De forma predeterminada, los miembros de la clase tienen el acceso [Public](../../../visual-basic/language-reference/modifiers/public.md), pero las variables y constantes tienen el acceso [Private](../../../visual-basic/language-reference/modifiers/private.md).  Cuando una clase tiene un acceso más restringido que uno de sus miembros, el nivel de acceso de la clase tiene prioridad.  
  
-   **Ámbito.** Una clase está en ámbito a lo largo de todo el espacio de nombres, clase, estructura o módulo que la contiene.  
  
     El ámbito de todos los miembros de la clase es la clase completa.  
  
     **Período de duración.** Visual Basic no admite las clases estáticas.  Un módulo proporciona el equivalente funcional de una clase estática.  Para obtener más información, vea [Module \(Instrucción\)](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     Los miembros de clase tienen duraciones que dependen de cómo y dónde se declaran.  Para obtener más información, vea [Período de duración en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   **Calificación.** El código que se encuentra fuera de una clase debe calificar el nombre de un miembro con el nombre de la clase.  
  
     Si el código de una clase anidada hace una referencia no calificada a un elemento de programación, Visual Basic busca el primer elemento en la clase anidada, después en su clase contenedora y así sucesivamente hasta llegar al elemento contenedor más externo.  
  
## Clases y módulos  
 Estos elementos tienen muchas similitudes, pero hay también algunas diferencias importantes.  
  
-   **Terminología.** Las versiones anteriores de Visual Basic reconocen dos tipos de módulos: *módulos de clase* \(archivos .cls\) y *módulos estándar* \(archivos .bas\).  En la versión actual se denominan *clases* y *módulos*, respectivamente.  
  
-   **Miembros compartidos.** Se puede controlar si un miembro de una clase es un miembro compartido o de instancia.  
  
-   **Orientación a objetos.** Las clases son orientadas a objetos, pero los módulos no lo son.  Se puede crear una o más instancias de una clase.  Para obtener más información, vea [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## Ejemplo  
 En el ejemplo siguiente se utiliza una instrucción `Class` para definir una clase y varios miembros.  
  
 [!code-vb[VbVbalrStatements#62](../../../visual-basic/language-reference/error-messages/codesnippet/visualbasic/class-statement_1.vb)]  
  
## Vea también  
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)   
 [Estructuras y clases](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)   
 [Interface \(Instrucción\)](../../../visual-basic/language-reference/statements/interface-statement.md)   
 [Module \(Instrucción\)](../../../visual-basic/language-reference/statements/module-statement.md)   
 [Property \(Instrucción\)](../../../visual-basic/language-reference/statements/property-statement.md)   
 [Duración de los objetos: cómo se crean y destruyen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)   
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)   
 [Cómo: Utilizar una clase genérica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)