---
title: Expresión with (referencia de C#)
description: Obtenga información sobre una expresión with que realiza la mutación no destructiva de registros de C#
ms.date: 11/12/2020
f1_keywords:
- with_CSharpKeyword
helpviewer_keywords:
- with expression [C#]
- with operator [C#]
ms.openlocfilehash: d7d3758c8c5da7859974b5b50b63d2a5ca16b24d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702230"
---
# <a name="with-expression-c-reference"></a><span data-ttu-id="08c1b-103">Expresión with (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="08c1b-103">with expression (C# reference)</span></span>

<span data-ttu-id="08c1b-104">Disponible en C# 9.0 y versiones posteriores, se trata de una expresión `with` que genera una copia de su operando [record](../../whats-new/csharp-9.md#record-types) con las propiedades y los campos especificados modificados:</span><span class="sxs-lookup"><span data-stu-id="08c1b-104">Available in C# 9.0 and later, a `with` expression produces a copy of its [record](../../whats-new/csharp-9.md#record-types) operand with the specified properties and fields modified:</span></span>

:::code language="csharp" source="snippets/with-expression/BasicExample.cs" :::

<span data-ttu-id="08c1b-105">Como se muestra en el ejemplo anterior, se usa la sintaxis de [ inicializador de objeto](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) para especificar qué miembros se van a modificar y sus nuevos valores.</span><span class="sxs-lookup"><span data-stu-id="08c1b-105">As the preceding example shows, you use [object initializer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) syntax to specify what members to modify and their new values.</span></span> <span data-ttu-id="08c1b-106">En una expresión `with`, un operando izquierdo debe ser de un tipo de registro.</span><span class="sxs-lookup"><span data-stu-id="08c1b-106">In a `with` expression, a left-hand operand must be of a record type.</span></span>

<span data-ttu-id="08c1b-107">El resultado de una expresión `with` tiene el mismo tipo de entorno de ejecución que el operando de la expresión, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="08c1b-107">The result of a `with` expression has the same runtime type as the expression's operand, as the following example shows:</span></span>

:::code language="csharp" source="snippets/with-expression/InheritanceExample.cs" :::

<span data-ttu-id="08c1b-108">En el caso de un miembro de tipo de referencia, cuando se copia un registro solo se copia la referencia a una instancia.</span><span class="sxs-lookup"><span data-stu-id="08c1b-108">In the case of a reference-type member, only the reference to an instance is copied when a record is copied.</span></span> <span data-ttu-id="08c1b-109">Tanto la copia como el registro original tienen acceso a la misma instancia de tipo de referencia.</span><span class="sxs-lookup"><span data-stu-id="08c1b-109">Both the copy and original record have access to the same reference-type instance.</span></span> <span data-ttu-id="08c1b-110">En el ejemplo siguiente se muestra ese comportamiento:</span><span class="sxs-lookup"><span data-stu-id="08c1b-110">The following example demonstrates that behavior:</span></span>

:::code language="csharp" source="snippets/with-expression/ExampleWithReferenceType.cs" :::

<span data-ttu-id="08c1b-111">Cualquier tipo de registro tiene el *constructor de copia*.</span><span class="sxs-lookup"><span data-stu-id="08c1b-111">Any record type has the *copy constructor*.</span></span> <span data-ttu-id="08c1b-112">Es un constructor con un único parámetro del tipo de registro contenedor.</span><span class="sxs-lookup"><span data-stu-id="08c1b-112">That is a constructor with a single parameter of the containing record type.</span></span> <span data-ttu-id="08c1b-113">Copia el estado de su argumento en una nueva instancia de registro.</span><span class="sxs-lookup"><span data-stu-id="08c1b-113">It copies the state of its argument to a new record instance.</span></span> <span data-ttu-id="08c1b-114">Al evaluar una expresión `with`, se llama al constructor de copia para crear instancias de una nueva instancia de registro en función de un registro original.</span><span class="sxs-lookup"><span data-stu-id="08c1b-114">At evaluation of a `with` expression, the copy constructor gets called to instantiate a new record instance based on an original record.</span></span> <span data-ttu-id="08c1b-115">Después, la nueva instancia se actualiza según las modificaciones especificadas.</span><span class="sxs-lookup"><span data-stu-id="08c1b-115">After that, the new instance gets updated according to the specified modifications.</span></span> <span data-ttu-id="08c1b-116">De forma predeterminada, el constructor de copia es implícito, es decir, lo genera el compilador.</span><span class="sxs-lookup"><span data-stu-id="08c1b-116">By default, the copy constructor is implicit, that is, compiler-generated.</span></span> <span data-ttu-id="08c1b-117">Si tiene que personalizar la semántica de la copia de registros, declare explícitamente un constructor de copia con el comportamiento deseado.</span><span class="sxs-lookup"><span data-stu-id="08c1b-117">If you need to customize the record copy semantics, explicitly declare a copy constructor with the desired behavior.</span></span> <span data-ttu-id="08c1b-118">En el ejemplo siguiente se actualiza el anterior con un constructor de copia explícito.</span><span class="sxs-lookup"><span data-stu-id="08c1b-118">The following example updates the preceding example with an explicit copy constructor.</span></span> <span data-ttu-id="08c1b-119">El nuevo comportamiento de copia consiste en copiar los elementos de lista en lugar de una referencia de lista cuando se copia un registro:</span><span class="sxs-lookup"><span data-stu-id="08c1b-119">The new copy behavior is to copy list items instead of a list reference when a record is copied:</span></span>

:::code language="csharp" source="snippets/with-expression/UserDefinedCopyConstructor.cs" :::

## <a name="c-language-specification"></a><span data-ttu-id="08c1b-120">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="08c1b-120">C# language specification</span></span>

<span data-ttu-id="08c1b-121">Para obtener más información, vea las secciones siguientes de la [nota de propuestas de características de registros](~/_csharplang/proposals/csharp-9.0/records.md):</span><span class="sxs-lookup"><span data-stu-id="08c1b-121">For more information, see the following sections of the [records feature proposal note](~/_csharplang/proposals/csharp-9.0/records.md):</span></span>

- [<span data-ttu-id="08c1b-122">Expresión `with`</span><span class="sxs-lookup"><span data-stu-id="08c1b-122">`with` expression</span></span>](~/_csharplang/proposals/csharp-9.0/records.md#with-expression)
- [<span data-ttu-id="08c1b-123">Copiar y clonar miembros</span><span class="sxs-lookup"><span data-stu-id="08c1b-123">Copy and Clone members</span></span>](~/_csharplang/proposals/csharp-9.0/records.md#copy-and-clone-members)

## <a name="see-also"></a><span data-ttu-id="08c1b-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="08c1b-124">See also</span></span>

- [<span data-ttu-id="08c1b-125">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="08c1b-125">C# reference</span></span>](../index.md)
- [<span data-ttu-id="08c1b-126">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="08c1b-126">C# operators and expressions</span></span>](index.md)
