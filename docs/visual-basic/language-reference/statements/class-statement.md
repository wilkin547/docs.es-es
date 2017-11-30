---
title: "Instrucción Class (Visual Basic)"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords: vb.Class
helpviewer_keywords:
- class modules
- Class statement [Visual Basic]
- classes [Visual Basic], fields
- fields [Visual Basic], of classes
- class types [Visual Basic], class statements
- classes [Visual Basic], creating
- classes [Visual Basic], data members
- data members [Visual Basic], of classes
ms.assetid: f2664f38-eb5a-4d4b-a374-1d041521fb6c
caps.latest.revision: "29"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: df86ef0eec67d96f2f997dc5dac7ee2357c6362b
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="class-statement-visual-basic"></a>Instrucción Class (Visual Basic)
Declara el nombre de una clase e introduce la definición de las variables, propiedades, eventos y procedimientos que incluye la clase.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ MustInherit | NotInheritable ] [ Partial ] _  
Class name [ ( Of typelist ) ]  
    [ Inherits classname ]  
    [ Implements interfacenames ]  
    [ statements ]  
End Class  
```  
  
## <a name="parts"></a>Elementos  
  
|Término|Definición|  
|---|---|  
|`attributelist`|Opcional. Vea [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Opcional. Puede ser uno de los siguientes:<br /><br /> -   [Público](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [Protegido](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [Privada](../../../visual-basic/language-reference/modifiers/private.md)<br />-   `Protected Friend`<br /><br /> Vea [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Opcional. Vea [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Opcional. Vea [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Opcional. Vea [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`Partial`|Opcional. Indica una definición parcial de la clase. Vea [parcial](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Obligatorio. Nombre de esta clase. Vea [nombres de elementos declarados](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Opcional. Especifica que se trata de una clase genérica.|  
|`typelist`|Es obligatorio si se utiliza la [de](../../../visual-basic/language-reference/statements/of-clause.md) palabra clave. Lista de parámetros de tipo para esta clase. Vea [escriba lista](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Opcional. Indica que esta clase hereda a los miembros de otra clase. Vea [Inherits (instrucción)](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Es obligatorio si se utiliza la instrucción `Inherits`. El nombre de la clase del que se deriva esta clase.|  
|`Implements`|Opcional. Indica que esta clase implementa a los miembros de una o varias interfaces. Vea [implementa instrucción](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Es obligatorio si se utiliza la instrucción `Implements`. Los nombres de las interfaces implementadas por esta clase.|  
|`statements`|Opcional. Instrucciones que definen a los miembros de esta clase.|  
|`End Class`|Obligatorio. Termina la definición de `Class`.|  
  
## <a name="remarks"></a>Comentarios  
 Un `Class` instrucción define un nuevo tipo de datos. A *clase* es un bloque de creación fundamental de la programación orientada a objetos (OOP). Para obtener más información, consulte [objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
 `Class` solo se puede utilizar en un espacio de nombres o un nivel de módulo. Esto significa que la *contexto de la declaración* para una clase debe ser un archivo de código fuente, espacio de nombres, clase, estructura, módulo o interfaz y no puede ser un procedimiento o bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 Cada instancia de una clase tiene un período de duración independiente de todas las demás instancias. Este período de duración comienza cuando se crea un [New (operador)](../../../visual-basic/language-reference/operators/new-operator.md) cláusula o por una función como <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>. Finaliza cuando todas las variables que señalan a la instancia se han establecido en [nada](../../../visual-basic/language-reference/nothing.md) o instancias de otras clases.  
  
 Clases de forma predeterminada, [Friend](../../../visual-basic/language-reference/modifiers/friend.md) acceso. Los niveles de acceso se pueden ajustar con los modificadores de acceso. Para obtener más información, consulte [tener acceso a niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Reglas  
  
-   **Anidamiento.** Puede definir una clase dentro de otra. La clase exterior se denomina la *que contiene la clase*, y la clase interna se denomina un *clase anidada*.  
  
-   **Herencia.** Si la clase utiliza el [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md), puede especificar sólo una clase base o interfaz. Una clase no puede heredar de más de un elemento.  
  
     Una clase no puede heredar de otra clase con un nivel de acceso más restrictivo. Por ejemplo, un `Public` clase no puede heredar de un `Friend` clase.  
  
     Una clase no puede heredar de una clase anidada dentro de él.  
  
-   **Implementación de.** Si la clase utiliza el [Implements (instrucción)](../../../visual-basic/language-reference/statements/implements-statement.md), debe implementar cada miembro definido por cada interfaz que se especifique en `interfacenames`. Una excepción a esto es la reimplementación de un miembro de clase base. Para obtener más información, vea "Implementación" en [implementa](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
-   **Propiedad Default.** Una clase puede especificar a lo sumo una propiedad como su *propiedad predeterminada*. Para obtener más información, consulte [predeterminado](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Nivel de acceso.** Dentro de una clase puede declarar a cada miembro con su propio nivel de acceso. De forma predeterminada los miembros de clase [público](../../../visual-basic/language-reference/modifiers/public.md) tener acceso, excepto las variables y constantes, que de forma predeterminada [privada](../../../visual-basic/language-reference/modifiers/private.md) acceso. Cuando una clase más restringió el acceso a uno de sus miembros, el nivel de acceso de la clase tiene prioridad.  
  
-   **Ámbito.** Una clase está en ámbito a lo largo de su espacio de nombres, clase, estructura o módulo que lo contiene.  
  
     El ámbito de cada miembro de clase es la clase completa.  
  
     **Duración.** Visual Basic no admite las clases estáticas. Un módulo proporciona el equivalente funcional de una clase estática. Para obtener más información, consulte [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     Los miembros de clase tienen duraciones dependiendo de cómo y dónde se declaran. Para obtener más información, consulte [duración en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   **Calificación.** Código fuera de una clase debe calificar el nombre de un miembro con el nombre de esa clase.  
  
     Si el código dentro de una clase anidada realiza una referencia sin calificar a un elemento de programación, Visual Basic busca el elemento en primer lugar de la clase anidada, a continuación, en su clase contenedora y así sucesivamente hasta el elemento contenedor principal.  
  
## <a name="classes-and-modules"></a>Las clases y módulos  
 Estos elementos tienen muchas similitudes, pero hay diferencias importantes.  
  
-   **Terminología.** Las versiones anteriores de Visual Basic reconocen dos tipos de módulos: *módulos de clase* (archivos de CLS) y *módulos estándar* (archivos de BAS). La versión actual llama a estos *clases* y *módulos*, respectivamente.  
  
-   **Miembros compartidos.** Puede controlar si un miembro de una clase es un compartido o miembro de instancia.  
  
-   **Orientación a objetos.** Clases están orientada a objetos, pero no son de módulos. Puede crear una o varias instancias de una clase. Para obtener más información, consulte [objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un `Class` instrucción para definir una clase y varios miembros.  
  
 [!code-vb[VbVbalrStatements#62](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/class-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también  
 [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)  
 [Estructuras y clases](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)  
 [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)  
 [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md)  
 [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)  
 [Duración de los objetos: cómo se crean y destruyen](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)  
 [Tipos genéricos en Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)  
 [Utilizar una clase genérica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
