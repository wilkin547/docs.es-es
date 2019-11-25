---
title: Structure (Instrucción)
ms.date: 05/12/2018
f1_keywords:
- vb.Structure
- Structure
helpviewer_keywords:
- user-defined types [Visual Basic], Structure statement
- compound data types [Visual Basic]
- Structure keyword [Visual Basic]
- Structure statement [Visual Basic]
- UDT (user-defined types)
- types [Visual Basic], user-defined
ms.assetid: 9bd1deea-2a89-4cdc-812c-6dcbb947c391
ms.openlocfilehash: 120f836b9d49c00e9c53af0d1fc832e22c8cbbb8
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/22/2019
ms.locfileid: "74346455"
---
# <a name="structure-statement"></a>Structure (Instrucción)

Declara el nombre de una estructura e introduce la definición de las variables, propiedades, eventos y procedimientos que la estructura incluye.

## <a name="syntax"></a>Sintaxis

```vb
[ <attributelist> ] [ accessmodifier ] [ Shadows ] [ Partial ] _
Structure name [ ( Of typelist ) ]
    [ Implements interfacenames ]
    [ datamemberdeclarations ]
    [ methodmemberdeclarations ]
End Structure
```

## <a name="parts"></a>Elementos

|Término|de esquema JSON|
|---|---|
|`attributelist`|Opcional. See [Attribute List](attribute-list.md).|
|`accessmodifier`|Opcional. Puede ser uno de los siguientes:<br /><br /> -   [Public](../modifiers/public.md)<br />-   [Protected](../modifiers/protected.md)<br />-   [Friend](../modifiers/friend.md)<br />-   [Private](../modifiers/private.md)<br />- [Protected Friend](../modifiers/protected-friend.md)<br/>- [Private Protected](../modifiers/private-protected.md) <br /><br /> Vea [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|
|`Shadows`|Opcional. See [Shadows](../modifiers/shadows.md).|
|`Partial`|Opcional. Indica una definición parcial de la estructura. See [Partial](../modifiers/partial.md).|
|`name`|Requerido. Nombre de esta estructura. Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
|`Of`|Opcional. Especifica que se trata de una estructura genérica.|
|`typelist`|Required if you use the [Of](of-clause.md) keyword. Lista de parámetros de tipo de esta estructura. See [Type List](type-list.md).|
|`Implements`|Opcional. Indica que esta estructura implementa los miembros de una o más interfaces. See [Implements Statement](implements-statement.md).|
|`interfacenames`|Es obligatorio si se utiliza la instrucción `Implements`. Nombres de las interfaces implementadas por esta estructura.|
|`datamemberdeclarations`|Requerido. Zero or more `Const`, `Dim`, `Enum`, or `Event` statements declaring *data members* of the structure.|
|`methodmemberdeclarations`|Opcional. Zero or more declarations of `Function`, `Operator`, `Property`, or `Sub` procedures, which serve as *method members* of the structure.|
|`End Structure`|Requerido. Termina la definición de `Structure`.|

## <a name="remarks"></a>Comentarios

La instrucción `Structure` define un tipo de valor compuesto que se puede personalizar. A *structure* is a generalization of the user-defined type (UDT) of previous versions of Visual Basic. For more information, see [Structures](../../programming-guide/language-features/data-types/structures.md).

Las estructuras admiten muchas de las mismas características que las clases. Por ejemplo, las estructuras pueden tener propiedades y procedimientos, pueden implementar interfaces y pueden tener constructores con parámetros. No obstante, existen diferencias importantes entre las estructuras y las clases en materias como la herencia, las declaraciones y la utilización. Además, las clases son tipos de referencia y las estructuras son tipos de valor. For more information, see [Structures and Classes](../../programming-guide/language-features/data-types/structures-and-classes.md).

`Structure` solo se puede utilizar en un espacio de nombres o un nivel de módulo. This means the *declaration context* for a structure must be a source file, namespace, class, structure, module, or interface, and cannot be a procedure or block. Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).

Structures default to [Friend](../modifiers/friend.md) access. Los niveles de acceso se pueden ajustar con los modificadores de acceso. For more information, see [Access levels in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

## <a name="rules"></a>Reglas

- **Nesting.** Puede definirse una estructura dentro de otra. The outer structure is called the *containing structure*, and the inner structure is called a *nested structure*. Sin embargo, no se puede tener acceso a los miembros de una estructura anidada a través de la estructura contenedora. En lugar de ello, se debe declarar una variable del tipo de datos de la estructura anidada.

- **Member Declaration.** Se debe declarar cada miembro de una estructura. A structure member cannot be [Protected](../modifiers/protected.md) or `Protected Friend` because nothing can inherit from a structure. La propia estructura, sin embargo, puede ser de tipo `Protected` o `Protected Friend`.
  
     En una estructura se pueden declarar cero o más variables no compartidas o eventos no compartidos y no personalizados. No pueden utilizarse únicamente constantes, propiedades y procedimientos, aunque algunos sean no compartidos.

- **Initialization.** No se puede inicializar el valor de ningún miembro de datos de una estructura no compartido como parte de su declaración. Dicho miembro de datos se debe inicializar mediante un constructor con parámetros en la estructura o bien mediante la asignación de un valor al miembro después de crear una instancia de la estructura.

- **Herencia.** Una estructura no puede heredar de ningún tipo distinto de <xref:System.ValueType>, del que todas las estructuras heredan. En particular, una estructura no puede heredar de otra.

     You cannot use the [Inherits Statement](inherits-statement.md) in a structure definition, even to specify <xref:System.ValueType>.

- **Implementation.** If the structure uses the [Implements Statement](implements-statement.md), you must implement every member defined by every interface you specify in `interfacenames`.

- **Default Property.** A structure can specify at most one property as its *default property*, using the [Default](../modifiers/default.md) modifier. For more information, see [Default](../modifiers/default.md).

## <a name="behavior"></a>Comportamiento

- **Access Level.** En una estructura, cada miembro se puede declarar con su propio nivel de acceso. All structure members default to [Public](../modifiers/public.md) access. Tenga en cuenta que si la propia estructura utiliza un nivel de acceso más limitado, se restringe automáticamente el acceso a sus miembros, aunque los niveles de acceso se ajusten con modificadores.

- **Scope.** Una estructura está en ámbito en su espacio de nombres, clase, estructura o módulo contenedores.

     El ámbito de todos los miembros de la estructura es la estructura completa.

- **Lifetime.** Una estructura no dispone por sí misma de período de duración. Más bien, cada instancia de esa estructura tiene un período de duración independiente de todas las demás instancias.

     The lifetime of an instance begins when it is created by a [New Operator](../operators/new-operator.md) clause. Finaliza cuando finaliza el período de duración de la variable que la contiene.

     No puede extender el período de duración de una instancia de estructura. Los módulos proporcionan una aproximación a la funcionalidad de estructura estática. For more information, see [Module Statement](module-statement.md).

     Los miembros de estructura disponen de un período de duración en función de cómo y donde se declaran. For more information, see "Lifetime" in [Class Statement](class-statement.md).

- **Qualification.** El código que se incluye fuera de una estructura debe calificar el nombre de un miembro con el nombre de dicha estructura.

     Si el código incluido en una estructura anidada realiza una referencia sin calificar a un elemento de programación, Visual Basic busca este elemento en la estructura anidada en primer lugar, a continuación en la estructura contenedora y así sucesivamente hasta el elemento contenedor principal. Para obtener más información, consulta [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

- **Memory Consumption.** Al igual que sucede con los demás tipos de datos compuestos, no puede calcularse de forma precisa el consumo total de memoria de una estructura sumando las asignaciones de almacenamiento nominal de sus miembros. Es más, no puede suponerse que el orden de almacenamiento en memoria sea el mismo que el orden de la declaración. Si necesita controlar el diseño de almacenamiento de una estructura, puede aplicar el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> a la instrucción `Structure`.

## <a name="example"></a>Ejemplo

En el siguiente ejemplo se utiliza la instrucción `Structure` para definir un conjunto de datos relacionados de un empleado. Se muestra el uso de los miembros `Public`, `Friend` y `Private` para reflejar la confidencialidad de los elementos de datos. También se muestran los miembros de evento, propiedad y procedimiento.

[!code-vb[VbVbalrStatements#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#57)]

For more information on how to use `Structure`s, see [Structure Variable](../../programming-guide/language-features/data-types/structure-variables.md).

## <a name="see-also"></a>Vea también

- [Class (instrucción)](class-statement.md)
- [Interface (instrucción)](interface-statement.md)
- [Module (instrucción)](module-statement.md)
- [Dim (instrucción)](dim-statement.md)
- [Const (instrucción)](const-statement.md)
- [Enum (instrucción)](enum-statement.md)
- [Event (instrucción)](event-statement.md)
- [Operator (instrucción)](operator-statement.md)
- [Property (instrucción)](property-statement.md)
- [Estructuras y clases](../../programming-guide/language-features/data-types/structures-and-classes.md)
