---
description: 'Operador new: referencia de C#'
title: 'Operador new: referencia de C#'
ms.date: 10/02/2020
f1_keywords:
- new_CSharpKeyword
helpviewer_keywords:
- new operator keyword [C#]
ms.assetid: a212b697-a79b-4105-9923-1f7b108036e8
ms.openlocfilehash: 3125f3d2c694dcfc5682ee482f3f76072ac3726d
ms.sourcegitcommit: 97405ed212f69b0a32faa66a5d5fae7e76628b68
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2020
ms.locfileid: "91609387"
---
# <a name="new-operator-c-reference"></a><span data-ttu-id="a8ba7-103">Operador new (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="a8ba7-103">new operator (C# reference)</span></span>

<span data-ttu-id="a8ba7-104">El operador `new` crea una nueva instancia de un tipo.</span><span class="sxs-lookup"><span data-stu-id="a8ba7-104">The `new` operator creates a new instance of a type.</span></span>

<span data-ttu-id="a8ba7-105">También puede usar la palabra clave `new` como un [modificador de declaración de miembro](../keywords/new-modifier.md) o una [restricción de tipo genérico](../keywords/new-constraint.md).</span><span class="sxs-lookup"><span data-stu-id="a8ba7-105">You can also use the `new` keyword as a [member declaration modifier](../keywords/new-modifier.md) or a [generic type constraint](../keywords/new-constraint.md).</span></span>

## <a name="constructor-invocation"></a><span data-ttu-id="a8ba7-106">Invocación del constructor</span><span class="sxs-lookup"><span data-stu-id="a8ba7-106">Constructor invocation</span></span>

<span data-ttu-id="a8ba7-107">Para crear una nueva instancia de un tipo, normalmente se invoca uno de los [constructores](../../programming-guide/classes-and-structs/constructors.md) de ese tipo mediante el operador `new`:</span><span class="sxs-lookup"><span data-stu-id="a8ba7-107">To create a new instance of a type, you typically invoke one of the [constructors](../../programming-guide/classes-and-structs/constructors.md) of that type using the `new` operator:</span></span>

[!code-csharp-interactive[invoke constructor](snippets/shared/NewOperator.cs#Constructor)]

<span data-ttu-id="a8ba7-108">Puede usar un [inicializador de colección u objeto](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) con el operador`new` para crear una instancia e inicializar un objeto en una sola instrucción, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8ba7-108">You can use an [object or collection initializer](../../programming-guide/classes-and-structs/object-and-collection-initializers.md) with the `new` operator to instantiate and initialize an object in one statement, as the following example shows:</span></span>

[!code-csharp-interactive[constructor with initializer](snippets/shared/NewOperator.cs#ConstructorWithInitializer)]

<span data-ttu-id="a8ba7-109">A partir de C# 9.0, las expresiones de invocación del constructor tienen tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="a8ba7-109">Beginning with C# 9.0, constructor invocation expressions are target-typed.</span></span> <span data-ttu-id="a8ba7-110">Es decir, si se conoce el tipo de destino de una expresión, puede omitir un nombre de tipo, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8ba7-110">That is, if a target type of an expression is known, you can omit a type name, as the following example shows:</span></span>

:::code language="csharp" source="snippets/shared/NewOperator.cs" id="SnippetTargetTyped":::

<span data-ttu-id="a8ba7-111">Como se muestra en el ejemplo anterior, siempre se usan paréntesis en una expresión `new` con tipo de destino.</span><span class="sxs-lookup"><span data-stu-id="a8ba7-111">As the preceding example shows, you always use parentheses in a target-typed `new` expression.</span></span>

<span data-ttu-id="a8ba7-112">Si se desconoce el tipo de destino de una expresión `new` (por ejemplo, cuando se usa la palabra clave [`var`](../keywords/var.md)), se debe especificar un nombre de tipo.</span><span class="sxs-lookup"><span data-stu-id="a8ba7-112">If a target type of a `new` expression is unknown (for example, when you use the [`var`](../keywords/var.md) keyword), you must specify a type name.</span></span>

## <a name="array-creation"></a><span data-ttu-id="a8ba7-113">creación de matriz</span><span class="sxs-lookup"><span data-stu-id="a8ba7-113">Array creation</span></span>

<span data-ttu-id="a8ba7-114">También se usa el operador `new` para crear una instancia de matriz, como se muestra en el ejemplo siguiente:</span><span class="sxs-lookup"><span data-stu-id="a8ba7-114">You also use the `new` operator to create an array instance, as the following example shows:</span></span>

[!code-csharp-interactive[create array](snippets/shared/NewOperator.cs#Array)]

<span data-ttu-id="a8ba7-115">Utilice la sintaxis de inicialización de matriz para crear una instancia de matriz y rellenarla con los elementos en una sola instrucción.</span><span class="sxs-lookup"><span data-stu-id="a8ba7-115">Use array initialization syntax to create an array instance and populate it with elements in one statement.</span></span> <span data-ttu-id="a8ba7-116">En el ejemplo siguiente se muestran varias maneras de hacerlo:</span><span class="sxs-lookup"><span data-stu-id="a8ba7-116">The following example shows various ways how you can do that:</span></span>

[!code-csharp-interactive[initialize array](snippets/shared/NewOperator.cs#ArrayInitialization)]

<span data-ttu-id="a8ba7-117">Para obtener más información sobre las matrices, consulte [Matrices](../../programming-guide/arrays/index.md).</span><span class="sxs-lookup"><span data-stu-id="a8ba7-117">For more information about arrays, see [Arrays](../../programming-guide/arrays/index.md).</span></span>

## <a name="instantiation-of-anonymous-types"></a><span data-ttu-id="a8ba7-118">Creación de instancias de tipos anónimos</span><span class="sxs-lookup"><span data-stu-id="a8ba7-118">Instantiation of anonymous types</span></span>

<span data-ttu-id="a8ba7-119">Para crear una instancia de un [tipo anónimo](../../programming-guide/classes-and-structs/anonymous-types.md), utilice el operador `new` y la sintaxis de inicializador de objeto:</span><span class="sxs-lookup"><span data-stu-id="a8ba7-119">To create an instance of an [anonymous type](../../programming-guide/classes-and-structs/anonymous-types.md), use the `new` operator and object initializer syntax:</span></span>

[!code-csharp-interactive[anonymous type](snippets/shared/NewOperator.cs#AnonymousType)]

## <a name="destruction-of-type-instances"></a><span data-ttu-id="a8ba7-120">Destrucción de instancias de tipo</span><span class="sxs-lookup"><span data-stu-id="a8ba7-120">Destruction of type instances</span></span>

<span data-ttu-id="a8ba7-121">No tiene que destruir instancias de tipo creadas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="a8ba7-121">You don't have to destroy earlier created type instances.</span></span> <span data-ttu-id="a8ba7-122">Las instancias de tipos de valor y referencia se destruyen automáticamente.</span><span class="sxs-lookup"><span data-stu-id="a8ba7-122">Instances of both reference and value types are destroyed automatically.</span></span> <span data-ttu-id="a8ba7-123">Las instancias de tipos de valor se destruyen en cuanto se destruye el contexto que los contiene.</span><span class="sxs-lookup"><span data-stu-id="a8ba7-123">Instances of value types are destroyed as soon as the context that contains them is destroyed.</span></span> <span data-ttu-id="a8ba7-124">Las instancias de tipos de referencia los destruye el [recolector de elementos no utilizados](../../../standard/garbage-collection/index.md) en un momento no especificado después de eliminarse la última referencia a ellos.</span><span class="sxs-lookup"><span data-stu-id="a8ba7-124">Instances of reference types are destroyed by the [garbage collector](../../../standard/garbage-collection/index.md) at some unspecified time after the last reference to them is removed.</span></span>

<span data-ttu-id="a8ba7-125">Para los tipos de instancia que contienen recursos no administrados, como un identificador de archivo, se recomienda realizar una limpieza determinista para asegurarse de que los recursos que contienen se liberan tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="a8ba7-125">For type instances that contain unmanaged resources, for example, a file handle, it's recommended to employ deterministic clean-up to ensure that the resources they contain are released as soon as possible.</span></span> <span data-ttu-id="a8ba7-126">Para más información, vea la referencia de la API <xref:System.IDisposable?displayProperty=nameWithType> y el artículo sobre la [instrucción using](../keywords/using-statement.md).</span><span class="sxs-lookup"><span data-stu-id="a8ba7-126">For more information, see the <xref:System.IDisposable?displayProperty=nameWithType> API reference and the [using statement](../keywords/using-statement.md) article.</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="a8ba7-127">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="a8ba7-127">Operator overloadability</span></span>

<span data-ttu-id="a8ba7-128">Un tipo definido por el usuario no puede sobrecargar el operador `new`.</span><span class="sxs-lookup"><span data-stu-id="a8ba7-128">A user-defined type cannot overload the `new` operator.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="a8ba7-129">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="a8ba7-129">C# language specification</span></span>

<span data-ttu-id="a8ba7-130">Para más información, vea la sección [El operador new](~/_csharplang/spec/expressions.md#the-new-operator) de la [Especificación del lenguaje C#](~/_csharplang/spec/introduction.md).</span><span class="sxs-lookup"><span data-stu-id="a8ba7-130">For more information, see [The new operator](~/_csharplang/spec/expressions.md#the-new-operator) section of the [C# language specification](~/_csharplang/spec/introduction.md).</span></span>

<span data-ttu-id="a8ba7-131">Para más información sobre la expresión `new` con tipo de destino, consulte la [nota de propuesta de características](~/_csharplang/proposals/csharp-9.0/target-typed-new.md).</span><span class="sxs-lookup"><span data-stu-id="a8ba7-131">For more information about a target-typed `new` expression, see the [feature proposal note](~/_csharplang/proposals/csharp-9.0/target-typed-new.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="a8ba7-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="a8ba7-132">See also</span></span>

- [<span data-ttu-id="a8ba7-133">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="a8ba7-133">C# reference</span></span>](../index.md)
- [<span data-ttu-id="a8ba7-134">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="a8ba7-134">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="a8ba7-135">Inicializadores de objeto y colección</span><span class="sxs-lookup"><span data-stu-id="a8ba7-135">Object and collection initializers</span></span>](../../programming-guide/classes-and-structs/object-and-collection-initializers.md)
