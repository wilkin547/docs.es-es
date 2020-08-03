---
title: 'Campos: Guía de programación de C#'
description: Un campo de C# es una variable de cualquier tipo que se declara directamente en una clase o estructura. Los campos son miembros de su tipo contenedor.
ms.date: 07/20/2015
helpviewer_keywords:
- fields [C#]
ms.assetid: 3cbb2f61-75f8-4cce-b4ef-f5d1b3de0db7
ms.openlocfilehash: 9bd2e198cd623788a21d4da73e89851a6d77e3bb
ms.sourcegitcommit: cf5a800a33de64d0aad6d115ffcc935f32375164
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/20/2020
ms.locfileid: "86474792"
---
# <a name="fields-c-programming-guide"></a>Campos (Guía de programación de C#)

Un *campo* es una variable de cualquier tipo que se declara directamente en una [clase](../../language-reference/keywords/class.md) o [struct](../../language-reference/builtin-types/struct.md). Los campos son *miembros* de su tipo contenedor.

Una clase o struct puede tener campos de instancia, campos estáticos o ambos. Los campos de instancia son específicos de una instancia de un tipo. Si tiene una clase T, con un campo de instancia F, puede crear dos objetos de tipo T y modificar el valor de F en cada objeto sin afectar el valor del otro objeto. Por el contrario, un campo estático pertenece a la propia clase y se comparte entre todas las instancias de esa clase. Solo puede tener acceso al campo estático mediante el nombre de clase. Si obtiene acceso al campo estático mediante un nombre de instancia, obtendrá el error en tiempo de compilación [CS0176](../../misc/cs0176.md).

Por lo general, solo se deben usar campos para las variables que tienen accesibilidad privada o protegida. Los datos que la clase expone al código de cliente deben proporcionarse a través de [métodos](./methods.md), [propiedades](./properties.md) e [indizadores](../indexers/index.md). Mediante estas construcciones para el acceso indirecto a los campos internos, se puede proteger de los valores de entrada no válidos. Un campo privado que almacena los datos expuestos por una propiedad pública se denomina *memoria auxiliar* o *campo de respaldo*.

Los campos almacenan habitualmente los datos que deben ser accesibles para más de un método de clase y que deben almacenarse durante más tiempo de lo que dura un único método. Por ejemplo, es posible que una clase que representa una fecha de calendario tenga tres campos enteros: uno para el mes, otro para el día y otro para el año. Las variables que no se usan fuera del ámbito de un único método se deben declarar como *variables locales* dentro del campo del método.

Los campos se declaran en el bloque de clase especificando el nivel de acceso del campo, seguido por el tipo del campo, seguido por el nombre del campo. Por ejemplo:

[!code-csharp[csProgGuideObjects#61](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#61)]

Para obtener acceso a un campo en un objeto, agregue un punto después del nombre de objeto, seguido del nombre del campo, como en `objectname.fieldname`. Por ejemplo:

[!code-csharp[csProgGuideObjects#62](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#62)]

Se puede proporcionar un valor inicial a un campo mediante el operador de asignación cuando se declara el campo. Para asignar automáticamente el campo `day` a `"Monday"`, por ejemplo, se declararía `day` como en el ejemplo siguiente:

[!code-csharp[csProgGuideObjects#63](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#63)]

Los campos se inicializan inmediatamente antes de que se llame al constructor para la instancia del objeto. Si el constructor asigna el valor de un campo, sobrescribirá cualquier valor dado durante la declaración del campo. Para obtener más información, vea [Utilizar constructores](./using-constructors.md).

> [!NOTE]
> Un inicializador de campo no puede hacer referencia a otros campos de instancia.

Se pueden marcar campos como [público](../../language-reference/keywords/public.md), [privado](../../language-reference/keywords/private.md), [protegido](../../language-reference/keywords/protected.md), [interno](../../language-reference/keywords/internal.md), [protegido interno](../../language-reference/keywords/protected-internal.md) o [privado protegido](../../language-reference/keywords/private-protected.md). Estos modificadores de acceso definen cómo los usuarios de la clase pueden obtener acceso a los campos. Para obtener más información, consulte [Modificadores de acceso](./access-modifiers.md).

Opcionalmente, un campo se puede declarar como [static](../../language-reference/keywords/static.md). Esto hace que el campo esté disponible para los llamadores en cualquier momento, aunque no exista ninguna instancia de la clase. Para más información, vea [Clases estáticas y sus miembros](./static-classes-and-static-class-members.md).

Se puede declarar un campo como [readonly](../../language-reference/keywords/readonly.md). Solamente se puede asignar un valor a un campo de solo lectura durante la inicialización o en un constructor. Un campo `static readonly` es muy similar a una constante, salvo que el compilador de C# no tiene acceso al valor de un campo estático de solo lectura en tiempo de compilación, solo en tiempo de ejecución. Para obtener más información, vea [Constants](./constants.md) (Constantes).

## <a name="c-language-specification"></a>Especificación del lenguaje C#

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a>Vea también

- [Guía de programación de C#](../index.md)
- [Clases y structs](./index.md)
- [Utilizar constructores](./using-constructors.md)
- [Herencia](./inheritance.md)
- [Modificadores de acceso](./access-modifiers.md)
- [Clases y miembros de clase abstractos y sellados](./abstract-and-sealed-classes-and-class-members.md)
