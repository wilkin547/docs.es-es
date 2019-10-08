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
ms.openlocfilehash: 2e4514686afcbbe0e9ff0b3326c1be212db4f9f8
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005159"
---
# <a name="class-statement-visual-basic"></a>Instrucción Class (Visual Basic)
Declara el nombre de una clase e introduce la definición de las variables, propiedades, eventos y procedimientos que la clase incluye.  
  
## <a name="syntax"></a>Sintaxis  
  
```vb  
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
|`attributelist`|Opcional. Vea [lista de atributos](../../../visual-basic/language-reference/statements/attribute-list.md).|  
|`accessmodifier`|Opcional. Puede ser uno de los siguientes:<br /><br /> -   [público](../../../visual-basic/language-reference/modifiers/public.md)<br />-   [protegido](../../../visual-basic/language-reference/modifiers/protected.md)<br />-   [Friend](../../../visual-basic/language-reference/modifiers/friend.md)<br />-   [privado](../../../visual-basic/language-reference/modifiers/private.md)<br />[amigo protegido](../../language-reference/modifiers/protected-friend.md) -   <br />- [Private Protected](../../language-reference/modifiers/private-protected.md)<br/><br/> Vea [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Opcional. Vea [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md).|  
|`MustInherit`|Opcional. Vea [MustInherit](../../../visual-basic/language-reference/modifiers/mustinherit.md).|  
|`NotInheritable`|Opcional. Vea [NotInheritable](../../../visual-basic/language-reference/modifiers/notinheritable.md).|  
|`Partial`|Opcional. Indica una definición parcial de la clase. Vea [partial](../../../visual-basic/language-reference/modifiers/partial.md).|  
|`name`|Obligatorio. Nombre de esta clase. Vea [Declared Element Names](../../../visual-basic/programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Opcional. Especifica que se trata de una clase genérica.|  
|`typelist`|Obligatorio si se usa la palabra clave [of](../../../visual-basic/language-reference/statements/of-clause.md) . Lista de parámetros de tipo de esta clase. Consulte [lista de tipos](../../../visual-basic/language-reference/statements/type-list.md).|  
|`Inherits`|Opcional. Indica que esta clase hereda los miembros de otra clase. Vea [Inherits (instrucción](../../../visual-basic/language-reference/statements/inherits-statement.md)).|  
|`classname`|Es obligatorio si se utiliza la instrucción `Inherits`. Nombre de la clase de la que se deriva esta clase.|  
|`Implements`|Opcional. Indica que esta clase implementa los miembros de una o más interfaces. Vea [Implements (instrucción](../../../visual-basic/language-reference/statements/implements-statement.md)).|  
|`interfacenames`|Es obligatorio si se utiliza la instrucción `Implements`. Los nombres de las interfaces que implementa esta clase.|  
|`statements`|Opcional. Instrucciones que definen los miembros de esta clase.|  
|`End Class`|Obligatorio. Termina la definición de `Class`.|  
  
## <a name="remarks"></a>Comentarios  
 Una instrucción `Class` define un nuevo tipo de datos. Una *clase* es un bloque de creación fundamental de la programación orientada a objetos (OOP). Para obtener más información, vea [objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
 `Class` solo se puede utilizar en un espacio de nombres o un nivel de módulo. Esto significa que el contexto de la *declaración* de una clase debe ser un archivo de código fuente, un espacio de nombres, una clase, una estructura, un módulo o una interfaz y no puede ser un procedimiento o un bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](../../../visual-basic/language-reference/statements/declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 Cada instancia de una clase tiene una duración independiente de todas las demás instancias. Esta duración comienza cuando la crea una nueva cláusula de [operador](../../../visual-basic/language-reference/operators/new-operator.md) o una función como <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A>. Finaliza cuando todas las variables que apuntan a la instancia se han establecido en [Nothing](../../../visual-basic/language-reference/nothing.md) o en instancias de otras clases.  
  
 Las clases tienen acceso de forma predeterminada a [Friend](../../../visual-basic/language-reference/modifiers/friend.md) . Los niveles de acceso se pueden ajustar con los modificadores de acceso. Para obtener más información, consulte [niveles de acceso en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Reglas  
  
- **Anidamiento.** Puede definir una clase dentro de otra. La clase externa se denomina *clase contenedora*y la clase interna se denomina *clase anidada*.  
  
- **Herencia.** Si la clase usa la [instrucción Inherits](../../../visual-basic/language-reference/statements/inherits-statement.md), solo puede especificar una clase base o una interfaz. Una clase no puede heredar de más de un elemento.  
  
     Una clase no puede heredar de otra clase con un nivel de acceso más restrictivo. Por ejemplo, una clase `Public` no puede heredar de una clase `Friend`.  
  
     Una clase no puede heredar de una clase anidada dentro de ella.  
  
- **Aplicación.** Si la clase usa la [instrucción Implements](../../../visual-basic/language-reference/statements/implements-statement.md), debe implementar todos los miembros definidos por cada interfaz que especifique en `interfacenames`. Una excepción a esto es la reimplementación de un miembro de clase base. Para obtener más información, vea el tema sobre la reimplementación en [implementaciones](../../../visual-basic/language-reference/statements/implements-clause.md).  
  
- **Propiedad predeterminada.** Una clase puede especificar como máximo una propiedad como su *propiedad predeterminada*. Para obtener más información, vea [default](../../../visual-basic/language-reference/modifiers/default.md).  
  
## <a name="behavior"></a>Comportamiento  
  
- **Nivel de acceso.** Dentro de una clase, puede declarar cada miembro con su propio nivel de acceso. Los miembros de clase tienen como valor predeterminado el acceso [público](../../../visual-basic/language-reference/modifiers/public.md) , excepto las variables y constantes, que tienen como valor predeterminado el acceso [privado](../../../visual-basic/language-reference/modifiers/private.md) . Cuando una clase tiene un acceso más restringido que uno de sus miembros, el nivel de acceso de la clase tiene prioridad.  
  
- **ID.** Una clase está en el ámbito A lo largo de su espacio de nombres, clase, estructura o módulo que lo contiene.  
  
     El ámbito de cada miembro de clase es toda la clase.  
  
     **Validez.** Visual Basic no admite clases estáticas. Un módulo proporciona el equivalente funcional de una clase estática. Para obtener más información, vea [Module Statement](../../../visual-basic/language-reference/statements/module-statement.md).  
  
     Los miembros de clase tienen duración en función de cómo y dónde se declaran. Para obtener más información, vea [duración en Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md).  
  
- **Evaluación.** El código fuera de una clase debe calificar el nombre de un miembro con el nombre de esa clase.  
  
     Si el código incluido en una clase anidada hace una referencia no calificada a un elemento de programación, Visual Basic busca el elemento en primer lugar en la clase anidada, luego en la clase contenedora y así sucesivamente hasta el elemento contenedor más externo.  
  
## <a name="classes-and-modules"></a>Clases y módulos  
 Estos elementos tienen muchas similitudes, pero también hay algunas diferencias importantes.  
  
- **Terminología.** Las versiones anteriores de Visual Basic reconocen dos tipos de módulos: *módulos de clase* (archivos. CLS) y *módulos estándar* (archivos. Bas). La versión actual llama a estas *clases* y *módulos*, respectivamente.  
  
- **Miembros compartidos.** Puede controlar si un miembro de una clase es un miembro compartido o de instancia.  
  
- **Orientación de objeto.** Las clases están orientadas a objetos, pero los módulos no lo son. Puede crear una o varias instancias de una clase. Para obtener más información, vea [objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="example"></a>Ejemplo  
 En el ejemplo siguiente se usa una instrucción `Class` para definir una clase y varios miembros.  
  
 [!code-vb[VbVbalrStatements#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#62)]  
  
## <a name="see-also"></a>Vea también

- [Objetos y clases](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
- [Estructuras y clases](../../../visual-basic/programming-guide/language-features/data-types/structures-and-classes.md)
- [Interface (instrucción)](../../../visual-basic/language-reference/statements/interface-statement.md)
- [Module (instrucción)](../../../visual-basic/language-reference/statements/module-statement.md)
- [Property (instrucción)](../../../visual-basic/language-reference/statements/property-statement.md)
- @no__t 0Object: Cómo se crean y destruyen los objetos @ no__t-0
- [Generic Types in Visual Basic](../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
- [Cómo: Utilizar una clase genérica](../../../visual-basic/programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
