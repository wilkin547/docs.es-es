---
title: '! (permite valores NULL): referencia de C#'
ms.date: 10/11/2019
f1_keywords:
- '!_CSharpKeyword'
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 36bfa46cebd2b35c4985dfc23dbe84f8f5dc9201
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 03/14/2020
ms.locfileid: "78846334"
---
# <a name="-null-forgiving-operator-c-reference"></a><span data-ttu-id="f1ef4-103">!</span><span class="sxs-lookup"><span data-stu-id="f1ef4-103">!</span></span> <span data-ttu-id="f1ef4-104">(permite valores NULL) (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="f1ef4-104">(null-forgiving) operator (C# reference)</span></span>

<span data-ttu-id="f1ef4-105">Disponible en C# 8.0 y versiones posteriores, el operador `!` de postfijo unario es el operador que permite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="f1ef4-105">Available in C# 8.0 and later, the unary postfix `!` operator is the null-forgiving operator.</span></span> <span data-ttu-id="f1ef4-106">En un [contexto de anotación que admite un valor NULL](../../nullable-references.md#nullable-annotation-context) habilitado, se usa el operador que permite un valor NULL para declarar que la expresión `x` de un tipo de referencia no es `null`: `x!`.</span><span class="sxs-lookup"><span data-stu-id="f1ef4-106">In an enabled [nullable annotation context](../../nullable-references.md#nullable-annotation-context), you use the null-forgiving operator to declare that expression `x` of a reference type isn't `null`: `x!`.</span></span> <span data-ttu-id="f1ef4-107">El operador `!` de prefijo unario es el [operador lógico de negación](boolean-logical-operators.md#logical-negation-operator-).</span><span class="sxs-lookup"><span data-stu-id="f1ef4-107">The unary prefix `!` operator is the [logical negation operator](boolean-logical-operators.md#logical-negation-operator-).</span></span>

<span data-ttu-id="f1ef4-108">El operador que permite un valor NULL no tiene ningún efecto en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="f1ef4-108">The null-forgiving operator has no effect at run time.</span></span> <span data-ttu-id="f1ef4-109">Solo afecta al análisis de flujo estático del compilador al cambiar el estado NULL de la expresión.</span><span class="sxs-lookup"><span data-stu-id="f1ef4-109">It only affects the compiler's static flow analysis by changing the null state of the expression.</span></span> <span data-ttu-id="f1ef4-110">En tiempo de ejecución, la expresión `x!` se evalúa en el resultado de la expresión subyacente `x`.</span><span class="sxs-lookup"><span data-stu-id="f1ef4-110">At run time, expression `x!` evaluates to the result of the underlying expression `x`.</span></span>

<span data-ttu-id="f1ef4-111">Para obtener más información sobre la característica de tipos de referencia que admiten un valor NULL, consulte [Tipos de referencia que admiten un valor NULL](../../nullable-references.md).</span><span class="sxs-lookup"><span data-stu-id="f1ef4-111">For more information about the nullable reference types feature, see [Nullable reference types](../../nullable-references.md).</span></span>

## <a name="examples"></a><span data-ttu-id="f1ef4-112">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="f1ef4-112">Examples</span></span>

<span data-ttu-id="f1ef4-113">Uno de los casos de uso del operador que permite un valor NULL es probar la lógica de validación de argumentos.</span><span class="sxs-lookup"><span data-stu-id="f1ef4-113">One of the use cases of the null-forgiving operator is in testing the argument validation logic.</span></span> <span data-ttu-id="f1ef4-114">Por ejemplo, considere la siguiente clase:</span><span class="sxs-lookup"><span data-stu-id="f1ef4-114">For example, consider the following class:</span></span>

[!code-csharp[Person class](snippets/NullForgivingOperator.cs#PersonClass)]

<span data-ttu-id="f1ef4-115">Con el [marco de pruebas MSTest](../../../core/testing/unit-testing-with-mstest.md) puede crear la prueba siguiente para la lógica de validación en el constructor:</span><span class="sxs-lookup"><span data-stu-id="f1ef4-115">Using the [MSTest test framework](../../../core/testing/unit-testing-with-mstest.md), you can create the following test for the validation logic in the constructor:</span></span>

[!code-csharp[Person test](snippets/NullForgivingOperator.cs#TestPerson)]

<span data-ttu-id="f1ef4-116">Sin el operador que permite un valor NULL, el compilador genera la advertencia siguiente para el código anterior: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span><span class="sxs-lookup"><span data-stu-id="f1ef4-116">Without the null-forgiving operator, the compiler generates the following warning for the preceding code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span></span> <span data-ttu-id="f1ef4-117">Al usar el operador que permite un valor NULL, se notifica al compilador que lo esperado es que se pase `null` y no se debe advertir al respecto.</span><span class="sxs-lookup"><span data-stu-id="f1ef4-117">By using the null-forgiving operator, you inform the compiler that passing `null` is expected and shouldn't be warned about.</span></span>

<span data-ttu-id="f1ef4-118">También puede usar el operador que permite un valor NULL cuando sepa a ciencia cierta que una expresión no puede ser `null`, pero el compilador no consigue reconocerlo.</span><span class="sxs-lookup"><span data-stu-id="f1ef4-118">You also can use the null-forgiving operator when you definitely know that an expression cannot be `null` but the compiler doesn't manage to recognize that.</span></span> <span data-ttu-id="f1ef4-119">En el ejemplo siguiente, si el método `IsValid` devuelve `true`, su argumento no es `null` y puede desreferenciarlo de forma segura:</span><span class="sxs-lookup"><span data-stu-id="f1ef4-119">In the following example, if the `IsValid` method returns `true`, its argument is not `null` and you can safely dereference it:</span></span>

[!code-csharp[Use null-forgiving operator](snippets/NullForgivingOperator.cs#UseNullForgiving)]

<span data-ttu-id="f1ef4-120">Sin el operador que permite un valor NULL, el compilador genera la advertencia siguiente para el código `p.Name`: `Warning CS8602: Dereference of a possibly null reference`.</span><span class="sxs-lookup"><span data-stu-id="f1ef4-120">Without the null-forgiving operator, the compiler generates the following warning for the `p.Name` code: `Warning CS8602: Dereference of a possibly null reference`.</span></span>

<span data-ttu-id="f1ef4-121">Si puede modificar el método `IsValid`, puede usar el atributo [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) para notificar al compilador que un argumento del método `IsValid` no puede ser `null` cuando el método devuelve `true`:</span><span class="sxs-lookup"><span data-stu-id="f1ef4-121">If you can modify the `IsValid` method, you can use the [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) attribute to inform the compiler that an argument of the `IsValid` method cannot be `null` when the method returns `true`:</span></span>

[!code-csharp[Use an attribute](snippets/NullForgivingOperator.cs#UseAttribute)]

<span data-ttu-id="f1ef4-122">En el ejemplo anterior, no es necesario usar el operador que permite un valor NULL porque el compilador tiene suficiente información para averiguar que `p` no puede ser `null` en la instrucción `if`.</span><span class="sxs-lookup"><span data-stu-id="f1ef4-122">In the preceding example, you don't need to use the null-forgiving operator because the compiler has enough information to find out that `p` cannot be `null` inside the `if` statement.</span></span> <span data-ttu-id="f1ef4-123">Para más información sobre los atributos que permiten proporcionar información adicional sobre el estado NULL de una variable, vea [Actualización de las API con atributos para definir las expectativas NULL](../../nullable-attributes.md).</span><span class="sxs-lookup"><span data-stu-id="f1ef4-123">For more information about the attributes that allow you to provide additional information about the null state of a variable, see [Upgrade APIs with attributes to define null expectations](../../nullable-attributes.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="f1ef4-124">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="f1ef4-124">C# language specification</span></span>

<span data-ttu-id="f1ef4-125">Para obtener más información, consulte la sección [The null-forgiving operator](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) (El operador que admite valores NULL) del [borrador de la especificación de tipos de referencia que aceptan valores NULL](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span><span class="sxs-lookup"><span data-stu-id="f1ef4-125">For more information, see [The null-forgiving operator](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md#the-null-forgiving-operator) section of the [draft of the nullable reference types specification](~/_csharplang/proposals/csharp-8.0/nullable-reference-types-specification.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="f1ef4-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1ef4-126">See also</span></span>

- [<span data-ttu-id="f1ef4-127">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="f1ef4-127">C# reference</span></span>](../index.md)
- [<span data-ttu-id="f1ef4-128">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="f1ef4-128">C# operators</span></span>](index.md)
- [<span data-ttu-id="f1ef4-129">Tutorial: Diseño con tipos de referencia que admiten un valor NULL</span><span class="sxs-lookup"><span data-stu-id="f1ef4-129">Tutorial: Design with nullable reference types</span></span>](../../tutorials/nullable-reference-types.md)
