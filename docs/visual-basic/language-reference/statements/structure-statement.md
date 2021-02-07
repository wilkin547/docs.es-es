---
description: 'Más información acerca de: Structure (instrucción)'
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
ms.openlocfilehash: 338abe359491f02c25bdb33d996fb639f58f8b35
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99741073"
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

## <a name="parts"></a>Partes

|Término|Definición|
|---|---|
|`attributelist`|Opcional. Vea [lista de atributos](attribute-list.md).|
|`accessmodifier`|Opcional. Puede ser uno de los siguientes:<br /><br /> -   [Pública](../modifiers/public.md)<br />-   [Contra](../modifiers/protected.md)<br />-   [Respecto](../modifiers/friend.md)<br />-   [Privada](../modifiers/private.md)<br />- [Friend protegido](../modifiers/protected-friend.md)<br/>- [Privado protegido](../modifiers/private-protected.md) <br /><br /> Consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).|
|`Shadows`|Opcional. Vea [Shadows](../modifiers/shadows.md).|
|`Partial`|Opcional. Indica una definición parcial de la estructura. Vea [partial](../modifiers/partial.md).|
|`name`|Necesario. Nombre de esta estructura. Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).|
|`Of`|Opcional. Especifica que se trata de una estructura genérica.|
|`typelist`|Obligatorio si se usa la palabra clave [of](of-clause.md) . Lista de parámetros de tipo de esta estructura. Consulte [lista de tipos](type-list.md).|
|`Implements`|Opcional. Indica que esta estructura implementa los miembros de una o más interfaces. Vea [Implements (instrucción](implements-statement.md)).|
|`interfacenames`|Es obligatorio si se utiliza la instrucción `Implements`. Nombres de las interfaces implementadas por esta estructura.|
|`datamemberdeclarations`|Necesario. Cero o más `Const` `Dim` instrucciones,, `Enum` o `Event` que declaran miembros de *datos* de la estructura.|
|`methodmemberdeclarations`|Opcional. Cero o más declaraciones de los `Function` `Operator` procedimientos,, `Property` o `Sub` , que sirven como miembros del *método* de la estructura.|
|`End Structure`|Necesario. Termina la definición de `Structure`.|

## <a name="remarks"></a>Observaciones

La instrucción `Structure` define un tipo de valor compuesto que se puede personalizar. Una *estructura* es una generalización del tipo definido por el usuario (UDT) de versiones anteriores de Visual Basic. Para obtener más información, vea [estructuras](../../programming-guide/language-features/data-types/structures.md).

Las estructuras admiten muchas de las mismas características que las clases. Por ejemplo, las estructuras pueden tener propiedades y procedimientos, pueden implementar interfaces y pueden tener constructores con parámetros. No obstante, existen diferencias importantes entre las estructuras y las clases en materias como la herencia, las declaraciones y la utilización. Además, las clases son tipos de referencia y las estructuras son tipos de valor. Para obtener más información, vea [estructuras y clases](../../programming-guide/language-features/data-types/structures-and-classes.md).

`Structure` solo se puede utilizar en un espacio de nombres o un nivel de módulo. Esto significa que el contexto de la *declaración* de una estructura debe ser un archivo de código fuente, un espacio de nombres, una clase, una estructura, un módulo o una interfaz y no puede ser un procedimiento o un bloque. Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).

El acceso predeterminado de las estructuras es [Friend](../modifiers/friend.md) . Los niveles de acceso se pueden ajustar con los modificadores de acceso. Para obtener más información, consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

## <a name="rules"></a>Reglas

- **Anidamiento.** Puede definirse una estructura dentro de otra. La estructura exterior se denomina la *estructura contenedora* y la estructura interna se denomina *estructura anidada*. Sin embargo, no se puede tener acceso a los miembros de una estructura anidada a través de la estructura contenedora. En lugar de ello, se debe declarar una variable del tipo de datos de la estructura anidada.

- **Declaración de miembros.** Se debe declarar cada miembro de una estructura. Un miembro de estructura no se puede [proteger](../modifiers/protected.md) o porque no se `Protected Friend` puede heredar nada de una estructura. La propia estructura, sin embargo, puede ser de tipo `Protected` o `Protected Friend`.
  
     En una estructura se pueden declarar cero o más variables no compartidas o eventos no compartidos y no personalizados. No pueden utilizarse únicamente constantes, propiedades y procedimientos, aunque algunos sean no compartidos.

- **Inicial.** No se puede inicializar el valor de ningún miembro de datos de una estructura no compartido como parte de su declaración. Dicho miembro de datos se debe inicializar mediante un constructor con parámetros en la estructura o bien mediante la asignación de un valor al miembro después de crear una instancia de la estructura.

- **Ella.** Una estructura no puede heredar de ningún tipo distinto de <xref:System.ValueType>, del que todas las estructuras heredan. En particular, una estructura no puede heredar de otra.

     No se puede usar la [instrucción Inherits](inherits-statement.md) en una definición de estructura, incluso para especificar <xref:System.ValueType> .

- **Aplicación.** Si la estructura utiliza la [instrucción Implements](implements-statement.md), debe implementar todos los miembros definidos por cada interfaz que especifique en `interfacenames` .

- **Propiedad predeterminada.** Una estructura puede especificar como máximo una propiedad como su *propiedad predeterminada*, utilizando el modificador [predeterminado](../modifiers/default.md) . Para obtener más información, vea [default](../modifiers/default.md).

## <a name="behavior"></a>Comportamiento

- **Nivel de acceso.** En una estructura, cada miembro se puede declarar con su propio nivel de acceso. De forma predeterminada, todos los miembros de estructura tienen acceso [público](../modifiers/public.md) . Tenga en cuenta que si la propia estructura utiliza un nivel de acceso más limitado, se restringe automáticamente el acceso a sus miembros, aunque los niveles de acceso se ajusten con modificadores.

- **Ámbito.** Una estructura está en ámbito en su espacio de nombres, clase, estructura o módulo contenedores.

     El ámbito de todos los miembros de la estructura es la estructura completa.

- **Validez.** Una estructura no dispone por sí misma de período de duración. Más bien, cada instancia de esa estructura tiene un período de duración independiente de todas las demás instancias.

     La duración de una instancia comienza cuando se crea mediante una [nueva cláusula Operator](../operators/new-operator.md) . Finaliza cuando finaliza el período de duración de la variable que la contiene.

     No puede extender el período de duración de una instancia de estructura. Los módulos proporcionan una aproximación a la funcionalidad de estructura estática. Para obtener más información, vea [Module Statement](module-statement.md).

     Los miembros de estructura disponen de un período de duración en función de cómo y donde se declaran. Para obtener más información, vea "Lifetime" en la [instrucción Class](class-statement.md).

- **Evaluación.** El código que se incluye fuera de una estructura debe calificar el nombre de un miembro con el nombre de dicha estructura.

     Si el código incluido en una estructura anidada realiza una referencia sin calificar a un elemento de programación, Visual Basic busca este elemento en la estructura anidada en primer lugar, a continuación en la estructura contenedora y así sucesivamente hasta el elemento contenedor principal. Para obtener más información, consulta [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

- **Consumo de memoria.** Al igual que sucede con los demás tipos de datos compuestos, no puede calcularse de forma precisa el consumo total de memoria de una estructura sumando las asignaciones de almacenamiento nominal de sus miembros. Es más, no puede suponerse que el orden de almacenamiento en memoria sea el mismo que el orden de la declaración. Si necesita controlar el diseño de almacenamiento de una estructura, puede aplicar el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> a la instrucción `Structure`.

## <a name="example"></a>Ejemplo

En el siguiente ejemplo se utiliza la instrucción `Structure` para definir un conjunto de datos relacionados de un empleado. Se muestra el uso de los miembros `Public`, `Friend` y `Private` para reflejar la confidencialidad de los elementos de datos. También se muestran los miembros de evento, propiedad y procedimiento.

[!code-vb[VbVbalrStatements#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#57)]

Para obtener más información sobre cómo usar `Structure` s, vea [variable de estructura](../../programming-guide/language-features/data-types/structure-variables.md).

## <a name="see-also"></a>Vea también

- [Instrucción Class](class-statement.md)
- [Instrucción Interface](interface-statement.md)
- [Module (Instrucción)](module-statement.md)
- [Instrucción Dim](dim-statement.md)
- [Instrucción Const](const-statement.md)
- [Instrucción Enum](enum-statement.md)
- [Event (Instrucción)](event-statement.md)
- [Operator Statement](operator-statement.md)
- [Property Statement](property-statement.md)
- [Estructuras y clases](../../programming-guide/language-features/data-types/structures-and-classes.md)
