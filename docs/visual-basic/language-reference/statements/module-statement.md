---
description: 'Más información acerca de: Module (instrucción)'
title: Module (Instrucción)
ms.date: 07/20/2015
f1_keywords:
- Module
- vb.Module
helpviewer_keywords:
- modules, classes
- modules
- Module statement [Visual Basic]
- modules, declaring
- standard modules
- classes [Visual Basic], vs. modules
- declarations [Visual Basic], modules
ms.assetid: a1243afc-14a5-45df-95d5-51118aeac362
ms.openlocfilehash: 2a19bcfa4521d34b5a91fbc9de412a6d8f6f39c0
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99768875"
---
# <a name="module-statement"></a>Module (Instrucción)

Declara el nombre de un módulo e introduce la definición de las variables, propiedades, eventos y procedimientos que el módulo incluye.

## <a name="syntax"></a>Sintaxis

```vb
[ <attributelist> ] [ accessmodifier ]  Module name
    [ statements ]
End Module
```

## <a name="parts"></a>Partes

`attributelist`  
Opcional. Vea [lista de atributos](attribute-list.md).

`accessmodifier`  
Opcional. Puede ser uno de los siguientes:

- [Público](../modifiers/public.md)

- [Friend](../modifiers/friend.md)

Consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

`name`  
Necesario. Nombre de este módulo. Vea [Declared Element Names](../../programming-guide/language-features/declared-elements/declared-element-names.md).

`statements`  
Opcional. Instrucciones que definen las variables, propiedades, eventos, procedimientos y tipos anidados de este módulo.

`End Module`  
Termina la definición de `Module`.

## <a name="remarks"></a>Observaciones

Una `Module` instrucción define un tipo de referencia disponible a lo largo de su espacio de nombres. Un *módulo* (a veces denominado *módulo estándar*) es similar a una clase, pero con algunas distinciones importantes. Cada módulo tiene exactamente una instancia y no es necesario crearla o asignarla a una variable. Los módulos no admiten la herencia ni implementan interfaces. Observe que un módulo no es un *tipo* en el sentido de que una clase o estructura es: no puede declarar un elemento de programación para que tenga el tipo de datos de un módulo.

Solo se puede usar `Module` en el nivel de espacio de nombres. Esto significa que el contexto de la *declaración* de un módulo debe ser un archivo de código fuente o un espacio de nombres, y no puede ser una clase, una estructura, un módulo, una interfaz, un procedimiento o un bloque. No se puede anidar un módulo dentro de otro módulo o dentro de cualquier tipo. Para obtener más información, vea [Declaration Contexts and Default Access Levels](declaration-contexts-and-default-access-levels.md) (Contextos de declaración y niveles de acceso predeterminados).

Un módulo tiene la misma duración que el programa. Como todos sus miembros `Shared` , también tienen una duración igual a la del programa.

El acceso predeterminado de los módulos es [Friend](../modifiers/friend.md) . Los niveles de acceso se pueden ajustar con los modificadores de acceso. Para obtener más información, consulte [niveles de acceso en Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).

Todos los miembros de un módulo son implícitamente `Shared` .

## <a name="classes-and-modules"></a>Clases y módulos

Estos elementos tienen muchas similitudes, pero también hay algunas diferencias importantes.

- **Terminología.** Las versiones anteriores de Visual Basic reconocen dos tipos de módulos: *módulos de clase* (archivos. CLS) y *módulos estándar* (archivos. Bas). La versión actual llama a estas *clases* y *módulos*, respectivamente.

- **Miembros compartidos.** Puede controlar si un miembro de una clase es un miembro compartido o de instancia.

- **Orientación de objeto.** Las clases están orientadas a objetos, pero los módulos no lo son. De modo que solo se pueden crear instancias de las clases como objetos. Para obtener más información, vea [objetos y clases](../../programming-guide/language-features/objects-and-classes/index.md).

## <a name="rules"></a>Reglas

- **Modificadores.** Todos los miembros de módulo están [compartidos](../modifiers/shared.md)implícitamente. No se puede usar la `Shared` palabra clave al declarar un miembro y no se puede modificar el estado compartido de ningún miembro.

- **Ella.** Un módulo no puede heredar de ningún tipo distinto de <xref:System.Object> , del que heredan todos los módulos. En concreto, un módulo no puede heredar de otro.

  No se puede usar la [instrucción Inherits](inherits-statement.md) en una definición de módulo, ni siquiera para especificar <xref:System.Object> .

- **Propiedad predeterminada.** No se puede definir ninguna propiedad predeterminada en un módulo. Para obtener más información, vea [default](../modifiers/default.md).

## <a name="behavior"></a>Comportamiento

- **Nivel de acceso.** Dentro de un módulo, puede declarar cada miembro con su propio nivel de acceso. Los miembros del módulo tienen acceso [público](../modifiers/public.md) de forma predeterminada, excepto las variables y constantes, que tienen como valor predeterminado el acceso [privado](../modifiers/private.md) . Cuando un módulo tiene más acceso restringido que uno de sus miembros, tiene prioridad el nivel de acceso del módulo especificado.

- **Ámbito.** Un módulo está en el ámbito A lo largo de su espacio de nombres.

  El ámbito de cada miembro del módulo es todo el módulo. Observe que todos los miembros se someten a la *promoción de tipos*, lo que hace que su ámbito se promueva al espacio de nombres que contiene el módulo. Para obtener más información, consulte [promoción de tipos](../../programming-guide/language-features/declared-elements/type-promotion.md).

- **Evaluación.** Puede tener varios módulos en un proyecto y puede declarar miembros con el mismo nombre en dos o más módulos. Sin embargo, debe calificar cualquier referencia a este miembro con el nombre de módulo adecuado si la referencia es de fuera de ese módulo. Para obtener más información, consulta [References to Declared Elements](../../programming-guide/language-features/declared-elements/references-to-declared-elements.md).

## <a name="example"></a>Ejemplo

[!code-vb[VbVbalrStatements#69](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStatements/VB/Class1.vb#69)]

## <a name="see-also"></a>Vea también

- [Instrucción Class](class-statement.md)
- [Namespace (Instrucción)](namespace-statement.md)
- [Structure (Instrucción)](structure-statement.md)
- [Instrucción Interface](interface-statement.md)
- [Property Statement](property-statement.md)
- [Promoción de tipos](../../programming-guide/language-features/declared-elements/type-promotion.md)
