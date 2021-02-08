---
description: 'Más información acerca de: User-Defined tipo de datos'
title: Tipo de datos definido por el usuario
ms.date: 07/20/2015
f1_keywords:
- UserDefined
- UDT
- vb.UDT
- User-Defined
- vb.UserDefined
- vb.User-Defined
helpviewer_keywords:
- user-defined data types [Visual Basic], Visual Basic
- user-defined types
- structures [Visual Basic], as user-defined data types
- user-defined types [Visual Basic], Visual Basic
- user-defined types [Visual Basic], structure declaration
- user-defined types [Visual Basic], structures in Visual Basic
- user-defined data types [Visual Basic], structure declaration
- data types [Visual Basic], assigning
- Structure statement [Visual Basic]
- data types [Visual Basic], user-defined
- user-defined data types [Visual Basic], structures in Visual Basic
- user-defined data types
- types [Visual Basic], user-defined
ms.assetid: be913dca-a364-4a51-96a1-549a1b390b0a
ms.openlocfilehash: 6eb94b38e2d29a4bbdfcf94de307bbe07a2c1b0c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99774972"
---
# <a name="user-defined-data-type"></a>Tipo de datos definido por el usuario

Contiene los datos en un formato definido por el usuario. La `Structure` instrucción define el formato.

Las versiones anteriores de Visual Basic admiten el tipo definido por el usuario (UDT). La versión actual expande el UDT a una *estructura*. Una estructura es una concatenación de uno o más *miembros* de varios tipos de datos. Visual Basic trata una estructura como una sola unidad, aunque también puede tener acceso a sus miembros individualmente.

## <a name="remarks"></a>Observaciones

Defina y use un tipo de datos de estructura cuando necesite combinar varios tipos de datos en una sola unidad, o cuando ninguno de los tipos de datos básicos satisfaga sus necesidades.

El valor predeterminado de un tipo de datos de estructura consta de la combinación de los valores predeterminados de cada uno de sus miembros.

## <a name="declaration-format"></a>Formato de declaración

Una declaración de estructura comienza con la [instrucción Structure](../statements/structure-statement.md) y termina con la `End Structure` instrucción. La `Structure` instrucción proporciona el nombre de la estructura, que también es el identificador del tipo de datos que la estructura está definiendo. Otras partes del código pueden utilizar este identificador para declarar variables, parámetros y valores devueltos por la función para que sean del tipo de datos de esta estructura.

Las declaraciones entre las `Structure` instrucciones y `End Structure` definen los miembros de la estructura.

## <a name="member-access-levels"></a>Niveles de acceso a miembros

Debe declarar cada miembro mediante una [instrucción Dim](../statements/dim-statement.md) o una instrucción que especifique el nivel de acceso, como [Public](../modifiers/public.md), [Friend](../modifiers/friend.md)o [Private](../modifiers/private.md). Si utiliza una `Dim` instrucción, el nivel de acceso predeterminado es Public.

## <a name="programming-tips"></a>Sugerencias de programación

- **Consumo de memoria.** Al igual que sucede con los demás tipos de datos compuestos, no puede calcularse de forma precisa el consumo total de memoria de una estructura sumando las asignaciones de almacenamiento nominal de sus miembros. Es más, no puede suponerse que el orden de almacenamiento en memoria sea el mismo que el orden de la declaración. Si necesita controlar el diseño de almacenamiento de una estructura, puede aplicar el atributo <xref:System.Runtime.InteropServices.StructLayoutAttribute> a la instrucción `Structure`.

- **Consideraciones de interoperabilidad.** Si interactúa con componentes que no se han escrito para el .NET Framework, por ejemplo, objetos de automatización o COM, tenga en cuenta que los tipos definidos por el usuario en otros entornos no son compatibles con los tipos de estructura de Visual Basic.

- **Ampliación.** No hay ninguna conversión automática a o desde cualquier tipo de datos de estructura. Puede definir operadores de conversión en la estructura mediante la [instrucción del operador](../statements/operator-statement.md)y puede declarar que cada operador de conversión sea `Widening` o `Narrowing` .

- **Caracteres de tipo.** Los tipos de datos de estructura no tienen un carácter de tipo literal o un carácter de tipo de identificador.

- **Tipo de Framework.** No hay ningún tipo correspondiente en el .NET Framework. Todas las estructuras heredan de la clase .NET Framework <xref:System.ValueType?displayProperty=nameWithType> , pero ninguna estructura individual corresponde a <xref:System.ValueType?displayProperty=nameWithType> .

## <a name="example"></a>Ejemplo

El paradigma siguiente muestra el contorno de la declaración de una estructura.

```vb
[Public | Protected | Friend | Protected Friend | Private] Structure structname
    {Dim | Public | Friend | Private} member1 As datatype1
    ' ...
    {Dim | Public | Friend | Private} memberN As datatypeN
End Structure
```

## <a name="see-also"></a>Vea también

- <xref:System.ValueType>
- <xref:System.Runtime.InteropServices.StructLayoutAttribute>
- [Tipo de datos](index.md)
- [Type Conversion Functions](../functions/type-conversion-functions.md)
- [Resumen de las conversiones](../keywords/conversion-summary.md)
- [Structure (Instrucción)](../statements/structure-statement.md)
- [Widening](../modifiers/widening.md)
- [Narrowing](../modifiers/narrowing.md)
- [Estructuras](../../programming-guide/language-features/data-types/structures.md)
- [Uso eficiente de los tipos de datos](../../programming-guide/language-features/data-types/efficient-use-of-data-types.md)
