---
title: Instrucción Class (Visual Basic)
ms.date: 05/12/2018
f1_keywords:
- vb.Class
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
ms.openlocfilehash: 846dc49f15f48e5f7f68171e0f937678751c796b
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54648669"
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
|`attributelist`|Opcional. Consulte [lista de los atributos](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Opcional. Puede ser uno de los siguientes:<br /><br /> -   [Public](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [protegido](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [privado](../../../visual-basic/language-reference/modifiers/private.md)<br />-   [Protected Friend](../../language-reference/modifiers/protected-friend.md)<br />- [Private protegida](../../language-reference/modifiers/private-protected.md)<br/><br/> Vea [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Opcional. Consulte [sombras](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Opcional. Consulte [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Opcional. Consulte [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`Partial`|Opcional. Indica una definición parcial de la clase. Consulte [parcial](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Obligatorio. Nombre de esta clase. Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Opcional. Especifica que se trata de una clase genérica.|  
|`typelist`|Obligatorio si se usa el [de](../../../visual-basic/language-reference/statements/of-clause.md) palabra clave. Lista de parámetros de tipo para esta clase. Consulte [escriba lista](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Opcional. Indica que esta clase hereda a los miembros de otra clase. Consulte [Inherits (instrucción)](../../../visual-basic/language-reference/statements/inherits-statement.md).|  
|`classname`|Es obligatorio si se utiliza la instrucción `Inherits`. El nombre de la clase del que se deriva esta clase.|  
|`Implements`|Opcional. Indica que esta clase implementa a los miembros de una o varias interfaces. Consulte [implementa instrucción](../../../visual-basic/language-reference/statements/implements-statement.md).|  
|`interfacenames`|Es obligatorio si se utiliza la instrucción `Implements`. Los nombres de las interfaces implementadas por esta clase.|  
|`statements`|Opcional. Instrucciones que definen a los miembros de esta clase.|  
|`End Class`|Obligatorio. Termina la definición de `Class`.|  
  
## <a name="remarks"></a>Comentarios  
 Un `Class` instrucción define un nuevo tipo de datos. Un *clase* es un bloque de creación fundamental de la programación orientada a objetos (OOP). Para obtener más información, consulte [objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
 `Class` solo se puede utilizar en un espacio de nombres o un nivel de módulo. Esto significa que el *contexto de declaración* para una clase debe ser un archivo de código fuente, espacio de nombres, clase, estructura, módulo o interfaz y no puede ser un procedimiento o bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 Cada instancia de una clase tiene un período de duración independiente de todas las demás instancias. Este período de duración comienza cuando se crea un [nuevo operador](../../../visual-basic/language-reference/operators/new-operator.md) cláusula o una función como <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>. Finaliza cuando se han establecido todas las variables que apunte a la instancia [nada](../../../visual-basic/language-reference/nothing.md) o a las instancias de otras clases.  
  
 Las clases de forma predeterminada [Friend](../../../visual-basic/language-reference/modifiers/friend.md) acceso. Los niveles de acceso se pueden ajustar con los modificadores de acceso. Para obtener más información, consulte [tener acceso a los niveles en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Reglas  
  
-   **Anidamiento.** Puede definir una clase dentro de otra. Se llama a la clase externa la *que contiene la clase*, y la clase interna se denomina un *clase anidada*.  
  
-   **Herencia.** Si la clase usa el [Inherits Statement](../../../visual-basic/language-reference/statements/inherits-statement.md), puede especificar sólo una clase base o interfaz. Una clase no puede heredar de más de un elemento.  
  
     Una clase no puede heredar de otra clase con un nivel de acceso más restrictivo. Por ejemplo, un `Public` clase no puede heredar de un `Friend` clase.  
  
     Una clase no puede heredar de una clase anidada dentro de él.  
  
-   **Implementación de.** Si la clase usa el [instrucción Implements](../../../visual-basic/language-reference/statements/implements-statement.md), debe implementar cada miembro definido por cada interfaz que se especifique en `interfacenames`. Una excepción a esto es la reimplementación de un miembro de clase base. Para obtener más información, vea "Reimplementación" en [implementa](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
-   **Propiedad predeterminada.** Una clase puede especificar como máximo una propiedad como su *propiedad predeterminada*. Para obtener más información, consulte [predeterminado](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Comportamiento  
  
-   **Nivel de acceso.** Dentro de una clase, puede declarar a cada miembro con su propio nivel de acceso. De forma predeterminada los miembros de clase [pública](../../../visual-basic/language-reference/modifiers/public.md) acceder, excepto las variables y constantes, que de forma predeterminada [privada](../../../visual-basic/language-reference/modifiers/private.md) acceso. Cuando una clase más restringió el acceso a uno de sus miembros, el nivel de acceso de la clase tiene prioridad.  
  
-   **Ámbito.** Es una clase en el ámbito de su espacio de nombres, clase, estructura o módulo que lo contiene.  
  
     El ámbito de cada miembro de clase es la clase completa.  
  
     **Duración.** Visual Basic no admite las clases estáticas. Un módulo proporciona el equivalente funcional de una clase estática. Para obtener más información, consulte [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     Los miembros de clase tienen duraciones dependiendo de cómo y dónde se declaran. Para obtener más información, consulte [duración en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
-   **Calificación.** Código fuera de una clase debe calificar el nombre de un miembro con el nombre de esa clase.  
  
     Si el código dentro de una clase anidada hace una referencia sin calificar a un elemento de programación, Visual Basic busca el elemento en primer lugar en la clase anidada, a continuación, en su clase contenedora, y así sucesivamente para el elemento contenedor.  
  
## <a name="classes-and-modules"></a>Las clases y módulos  
 Estos elementos tienen muchas similitudes, pero hay diferencias importantes.  
  
-   **Terminología.** Las versiones anteriores de Visual Basic reconocen dos tipos de módulos: *módulos de clase* (archivos .cls) y *módulos estándar* (archivos BAS). La versión actual llama a estos *clases* y *módulos*, respectivamente.  
  
-   **Miembros compartidos.** Puede controlar si un miembro de una clase es un compartido o un miembro de instancia.  
  
-   **Orientación a objetos.** Clases están orientada a objetos, pero no son de módulos. Puede crear una o varias instancias de una clase. Para obtener más información, consulte [objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa un `Class` instrucción para definir una clase y varios miembros.  
  
 [!code-vb[VbVbalrStatements#62](../../../visual-basic/language-reference/error-messages/codesnippet/VisualBasic/class-statement_1.vb)]  
  
## <a name="see-also"></a>Vea también
- [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Estructuras y clases](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md)
- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)
- [Duración del objeto: ¿Cómo se crean y destruyen objetos](../../../visual-basic/programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Cómo: Utilizar una clase genérica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
