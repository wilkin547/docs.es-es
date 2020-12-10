---
description: '! (permite valores NULL): referencia de C#'
title: '! (permite valores NULL): referencia de C#'
ms.date: 11/13/2020
f1_keywords:
- nullForgiving_CSharpKeyword
helpviewer_keywords:
- null-forgiving operator [C#]
- '! operator [C#]'
ms.openlocfilehash: 7b8c634404cf2f214cc4bee5d754443e9302a723
ms.sourcegitcommit: ecd9e9bb2225eb76f819722ea8b24988fe46f34c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/05/2020
ms.locfileid: "96739521"
---
# <a name="-null-forgiving-operator-c-reference"></a><span data-ttu-id="9c475-105">!</span><span class="sxs-lookup"><span data-stu-id="9c475-105">!</span></span> <span data-ttu-id="9c475-106">(permite valores NULL) (referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9c475-106">(null-forgiving) operator (C# reference)</span></span>

<span data-ttu-id="9c475-107">Disponible en C# 8.0 y versiones posteriores, el operador `!` de postfijo unario es el operador que permite valores NULL o supresión de valores NULL.</span><span class="sxs-lookup"><span data-stu-id="9c475-107">Available in C# 8.0 and later, the unary postfix `!` operator is the null-forgiving, or null-suppression, operator.</span></span> <span data-ttu-id="9c475-108">En un [contexto de anotación que admite un valor NULL](../../nullable-references.md#nullable-annotation-context) habilitado, se usa el operador que permite un valor NULL para declarar que la expresión `x` de un tipo de referencia no es `null`: `x!`.</span><span class="sxs-lookup"><span data-stu-id="9c475-108">In an enabled [nullable annotation context](../../nullable-references.md#nullable-annotation-context), you use the null-forgiving operator to declare that expression `x` of a reference type isn't `null`: `x!`.</span></span> <span data-ttu-id="9c475-109">El operador `!` de prefijo unario es el [operador lógico de negación](boolean-logical-operators.md#logical-negation-operator-).</span><span class="sxs-lookup"><span data-stu-id="9c475-109">The unary prefix `!` operator is the [logical negation operator](boolean-logical-operators.md#logical-negation-operator-).</span></span>

<span data-ttu-id="9c475-110">El operador que permite un valor NULL no tiene ningún efecto en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="9c475-110">The null-forgiving operator has no effect at run time.</span></span> <span data-ttu-id="9c475-111">Solo afecta al análisis de flujo estático del compilador al cambiar el estado NULL de la expresión.</span><span class="sxs-lookup"><span data-stu-id="9c475-111">It only affects the compiler's static flow analysis by changing the null state of the expression.</span></span> <span data-ttu-id="9c475-112">En tiempo de ejecución, la expresión `x!` se evalúa en el resultado de la expresión subyacente `x`.</span><span class="sxs-lookup"><span data-stu-id="9c475-112">At run time, expression `x!` evaluates to the result of the underlying expression `x`.</span></span>

<span data-ttu-id="9c475-113">Para obtener más información sobre la característica de tipos de referencia que admiten un valor NULL, consulte [Tipos de referencia que admiten un valor NULL](../builtin-types/nullable-reference-types.md).</span><span class="sxs-lookup"><span data-stu-id="9c475-113">For more information about the nullable reference types feature, see [Nullable reference types](../builtin-types/nullable-reference-types.md).</span></span>

## <a name="examples"></a><span data-ttu-id="9c475-114">Ejemplos</span><span class="sxs-lookup"><span data-stu-id="9c475-114">Examples</span></span>

<span data-ttu-id="9c475-115">Uno de los casos de uso del operador que permite un valor NULL es probar la lógica de validación de argumentos.</span><span class="sxs-lookup"><span data-stu-id="9c475-115">One of the use cases of the null-forgiving operator is in testing the argument validation logic.</span></span> <span data-ttu-id="9c475-116">Por ejemplo, considere la siguiente clase:</span><span class="sxs-lookup"><span data-stu-id="9c475-116">For example, consider the following class:</span></span>

[!code-csharp[Person class](snippets/shared/NullForgivingOperator.cs#PersonClass)]

<span data-ttu-id="9c475-117">Con el [marco de pruebas MSTest](../../../core/testing/unit-testing-with-mstest.md) puede crear la prueba siguiente para la lógica de validación en el constructor:</span><span class="sxs-lookup"><span data-stu-id="9c475-117">Using the [MSTest test framework](../../../core/testing/unit-testing-with-mstest.md), you can create the following test for the validation logic in the constructor:</span></span>

[!code-csharp[Person test](snippets/shared/NullForgivingOperator.cs#TestPerson)]

<span data-ttu-id="9c475-118">Sin el operador que permite un valor NULL, el compilador genera la advertencia siguiente para el código anterior: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span><span class="sxs-lookup"><span data-stu-id="9c475-118">Without the null-forgiving operator, the compiler generates the following warning for the preceding code: `Warning CS8625: Cannot convert null literal to non-nullable reference type`.</span></span> <span data-ttu-id="9c475-119">Al usar el operador que permite un valor NULL, se notifica al compilador que lo esperado es que se pase `null` y no se debe advertir al respecto.</span><span class="sxs-lookup"><span data-stu-id="9c475-119">By using the null-forgiving operator, you inform the compiler that passing `null` is expected and shouldn't be warned about.</span></span>

<span data-ttu-id="9c475-120">También puede usar el operador que permite valores NULL cuando sepa a ciencia cierta que una expresión no puede ser `null`, pero el compilador no consigue reconocerlo.</span><span class="sxs-lookup"><span data-stu-id="9c475-120">You can also use the null-forgiving operator when you definitely know that an expression cannot be `null` but the compiler doesn't manage to recognize that.</span></span> <span data-ttu-id="9c475-121">En el ejemplo siguiente, si el método `IsValid` devuelve `true`, su argumento no es `null` y puede desreferenciarlo de forma segura:</span><span class="sxs-lookup"><span data-stu-id="9c475-121">In the following example, if the `IsValid` method returns `true`, its argument is not `null` and you can safely dereference it:</span></span>

[!code-csharp[Use null-forgiving operator](snippets/shared/NullForgivingOperator.cs#UseNullForgiving)]

<span data-ttu-id="9c475-122">Sin el operador que permite un valor NULL, el compilador genera la advertencia siguiente para el código `p.Name`: `Warning CS8602: Dereference of a possibly null reference`.</span><span class="sxs-lookup"><span data-stu-id="9c475-122">Without the null-forgiving operator, the compiler generates the following warning for the `p.Name` code: `Warning CS8602: Dereference of a possibly null reference`.</span></span>

<span data-ttu-id="9c475-123">Si puede modificar el método `IsValid`, puede usar el atributo [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) para notificar al compilador que un argumento del método `IsValid` no puede ser `null` cuando el método devuelve `true`:</span><span class="sxs-lookup"><span data-stu-id="9c475-123">If you can modify the `IsValid` method, you can use the [NotNullWhen](xref:System.Diagnostics.CodeAnalysis.NotNullWhenAttribute) attribute to inform the compiler that an argument of the `IsValid` method cannot be `null` when the method returns `true`:</span></span>

[!code-csharp[Use an attribute](snippets/shared/NullForgivingOperator.cs#UseAttribute)]

<span data-ttu-id="9c475-124">En el ejemplo anterior, no es necesario usar el operador que permite un valor NULL porque el compilador tiene suficiente información para averiguar que `p` no puede ser `null` en la instrucción `if`.</span><span class="sxs-lookup"><span data-stu-id="9c475-124">In the preceding example, you don't need to use the null-forgiving operator because the compiler has enough information to find out that `p` cannot be `null` inside the `if` statement.</span></span> <span data-ttu-id="9c475-125">Para más información sobre los atributos que permiten proporcionar información adicional sobre el estado NULL de una variable, vea [Actualización de las API con atributos para definir las expectativas NULL](../attributes/nullable-analysis.md).</span><span class="sxs-lookup"><span data-stu-id="9c475-125">For more information about the attributes that allow you to provide additional information about the null state of a variable, see [Upgrade APIs with attributes to define null expectations](../attributes/nullable-analysis.md).</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9c475-126">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="9c475-126">C# language specification</span></span>

<span data-ttu-id="9c475-127">Para obtener más información, consulte la sección [The null-forgiving operator](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md#the-null-forgiving-operator) (El operador que admite valores NULL) del [borrador de la especificación de tipos de referencia que aceptan valores NULL](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md).</span><span class="sxs-lookup"><span data-stu-id="9c475-127">For more information, see [The null-forgiving operator](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md#the-null-forgiving-operator) section of the [draft of the nullable reference types specification](~/_csharplang/proposals/csharp-9.0/nullable-reference-types-specification.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9c475-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="9c475-128">See also</span></span>

- [<span data-ttu-id="9c475-129">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="9c475-129">C# reference</span></span>](../index.md)
- [<span data-ttu-id="9c475-130">Operadores y expresiones de C#</span><span class="sxs-lookup"><span data-stu-id="9c475-130">C# operators and expressions</span></span>](index.md)
- [<span data-ttu-id="9c475-131">Tutorial: Diseño con tipos de referencia que admiten un valor NULL</span><span class="sxs-lookup"><span data-stu-id="9c475-131">Tutorial: Design with nullable reference types</span></span>](../../tutorials/nullable-reference-types.md)
