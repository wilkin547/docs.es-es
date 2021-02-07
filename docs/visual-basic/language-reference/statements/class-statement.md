---
description: 'Más información sobre: instrucción Class (Visual Basic)'
title: Instrucción Class
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
ms.openlocfilehash: de4541addc9f4755d973586c7d1b4410e4bf12ed
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99673900"
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
  
## <a name="parts"></a>Partes  
  
|Término|Definición|  
|---|---|  
|`attributelist`|Opcional. Vea [lista de atributos](attribute-list.md).|  
|`accessmodifier`|Opcional. Puede ser uno de los siguientes:<br /><br /> -   [Pública](../modifiers/public.md)<br />-   [Contra](../modifiers/protected.md)<br />-   [Respecto](../modifiers/friend.md)<br />-   [Privada](../modifiers/private.md)<br />-   [Friend protegido](../modifiers/protected-friend.md)<br />- [Privado protegido](../modifiers/private-protected.md)<br/><br/> Consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|  
|`Shadows`|Opcional. Vea [Shadows](../modifiers/shadows.md).|  
|`MustInherit`|Opcional. Vea [MustInherit](../modifiers/mustinherit.md).|  
|`NotInheritable`|Opcional. Vea [NotInheritable](../modifiers/notinheritable.md).|  
|`Partial`|Opcional. Indica una definición parcial de la clase. Vea [partial](../modifiers/partial.md).|  
|`name`|Necesario. Nombre de esta clase. Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|  
|`Of`|Opcional. Especifica que se trata de una clase genérica.|  
|`typelist`|Obligatorio si se usa la palabra clave [of](of-clause.md) . Lista de parámetros de tipo de esta clase. Consulte [lista de tipos](type-list.md).|  
|`Inherits`|Opcional. Indica que esta clase hereda los miembros de otra clase. Vea [Inherits (instrucción](inherits-statement.md)).|  
|`classname`|Es obligatorio si se utiliza la instrucción `Inherits`. Nombre de la clase de la que se deriva esta clase.|  
|`Implements`|Opcional. Indica que esta clase implementa los miembros de una o más interfaces. Vea [Implements (instrucción](implements-statement.md)).|  
|`interfacenames`|Es obligatorio si se utiliza la instrucción `Implements`. Los nombres de las interfaces que implementa esta clase.|  
|`statements`|Opcional. Instrucciones que definen los miembros de esta clase.|  
|`End Class`|Necesario. Termina la definición de `Class`.|  
  
## <a name="remarks"></a>Observaciones  

 Una `Class` instrucción define un nuevo tipo de datos. Una *clase* es un bloque de creación fundamental de la programación orientada a objetos (OOP). Para obtener más información, vea [objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md).  
  
 `Class` solo se puede utilizar en un espacio de nombres o un nivel de módulo. Esto significa que el contexto de la *declaración* de una clase debe ser un archivo de código fuente, un espacio de nombres, una clase, una estructura, un módulo o una interfaz y no puede ser un procedimiento o un bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).  
  
 Cada instancia de una clase tiene una duración independiente de todas las demás instancias. Esta duración comienza cuando se crea mediante una nueva cláusula de [operador](../operators/new-operator.md) o mediante una función como <xref:Microsoft.VisualBasic.Interaction.CreateObject%2A> . Finaliza cuando todas las variables que apuntan a la instancia se han establecido en [Nothing](../nothing.md) o en instancias de otras clases.  
  
 Las clases tienen acceso de forma predeterminada a [Friend](../modifiers/friend.md) . Los niveles de acceso se pueden ajustar con los modificadores de acceso. Para obtener más información, consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="rules"></a>Reglas  
  
- **Anidamiento.** Puede definir una clase dentro de otra. La clase externa se denomina *clase contenedora* y la clase interna se denomina *clase anidada*.  
  
- **Ella.** Si la clase usa la [instrucción Inherits](inherits-statement.md), solo puede especificar una clase base o una interfaz. Una clase no puede heredar de más de un elemento.  
  
     Una clase no puede heredar de otra clase con un nivel de acceso más restrictivo. Por ejemplo, una `Public` clase no puede heredar de una `Friend` clase.  
  
     Una clase no puede heredar de una clase anidada dentro de ella.  
  
- **Aplicación.** Si la clase usa la [instrucción Implements](implements-statement.md), debe implementar todos los miembros definidos por cada interfaz que especifique en `interfacenames` . Una excepción a esto es la reimplementación de un miembro de clase base. Para obtener más información, vea el tema sobre la reimplementación en [implementaciones](implements-clause.md).  
  
- **Propiedad predeterminada.** Una clase puede especificar como máximo una propiedad como su *propiedad predeterminada*. Para obtener más información, vea [default](../modifiers/default.md).  
  
## <a name="behavior"></a>Comportamiento  
  
- **Nivel de acceso.** Dentro de una clase, puede declarar cada miembro con su propio nivel de acceso. Los miembros de clase tienen como valor predeterminado el acceso [público](../modifiers/public.md) , excepto las variables y constantes, que tienen como valor predeterminado el acceso [privado](../modifiers/private.md) . Cuando una clase tiene un acceso más restringido que uno de sus miembros, el nivel de acceso de la clase tiene prioridad.  
  
- **Ámbito.** Una clase está en el ámbito A lo largo de su espacio de nombres, clase, estructura o módulo que lo contiene.  
  
     El ámbito de cada miembro de clase es toda la clase.  
  
     **Validez.** Visual Basic no admite clases estáticas. Un módulo proporciona el equivalente funcional de una clase estática. Para obtener más información, vea [Module Statement](module-statement.md).  
  
     Los miembros de clase tienen duración en función de cómo y dónde se declaran. Para obtener más información, vea [duración en Visual Basic](../../programming-guide/language-features/declared-elements/lifetime.md).  
  
- **Evaluación.** El código fuera de una clase debe calificar el nombre de un miembro con el nombre de esa clase.  
  
     Si el código incluido en una clase anidada hace una referencia no calificada a un elemento de programación, Visual Basic busca el elemento en primer lugar en la clase anidada, luego en la clase contenedora y así sucesivamente hasta el elemento contenedor más externo.  
  
## <a name="classes-and-modules"></a>Clases y módulos  

 Estos elementos tienen muchas similitudes, pero también hay algunas diferencias importantes.  
  
- **Terminología.** Las versiones anteriores de Visual Basic reconocen dos tipos de módulos: *módulos de clase* (archivos. CLS) y *módulos estándar* (archivos. Bas). La versión actual llama a estas *clases* y *módulos*, respectivamente.  
  
- **Miembros compartidos.** Puede controlar si un miembro de una clase es un miembro compartido o de instancia.  
  
- **Orientación de objeto.** Las clases están orientadas a objetos, pero los módulos no lo son. Puede crear una o varias instancias de una clase. Para obtener más información, vea [objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md).  
  
## <a name="example"></a>Ejemplo  

 En el ejemplo siguiente se usa una `Class` instrucción para definir una clase y varios miembros.  
  
 [!code-vb[VbVbalrStatements#62](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#62)]  
  
## <a name="see-also"></a>Vea también

- [Objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md)
- [Estructuras y clases](../../programming-guide/language-features/data-types/structures-and-classes.md)
- [Instrucción Interface](interface-statement.md)
- [Module (Instrucción)](module-statement.md)
- [Property Statement](property-statement.md)
- [Duración de los objetos: cómo se crean y destruyen](../../programming-guide/language-features/objects-and-classes/object-lifetime-how-objects-are-created-and-destroyed.md)
- [Tipos genéricos en Visual Basic](../../programming-guide/language-features/data-types/generic-types.md)
- [Procedimiento Uso de clases genéricas](../../programming-guide/language-features/data-types/how-to-use-a-generic-class.md)
