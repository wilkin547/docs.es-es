---
title: '. : Referencia de C#'
ms.custom: seodec18
ms.date: 02/25/2019
f1_keywords:
- ._CSharpKeyword
helpviewer_keywords:
- member access operator (.) [C#]
- . operator [C#]
- dot operator (.) [C#]
ms.assetid: a1f54b52-b686-4ae5-a48e-a2a9ebd0eb7b
ms.openlocfilehash: 2661676d53deb874c5e5a90b4443b301730e09df
ms.sourcegitcommit: bd28ff1e312eaba9718c4f7ea272c2d4781a7cac
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 02/26/2019
ms.locfileid: "56836466"
---
# <a name="-operator-c-reference"></a><span data-ttu-id="9cb16-103">.</span><span class="sxs-lookup"><span data-stu-id="9cb16-103">.</span></span> <span data-ttu-id="9cb16-104">operator (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="9cb16-104">operator (C# Reference)</span></span>

<span data-ttu-id="9cb16-105">El punto (`.`) se suele usar para el acceso a miembros.</span><span class="sxs-lookup"><span data-stu-id="9cb16-105">The dot, `.`, is typically used for member access.</span></span>

<span data-ttu-id="9cb16-106">Use el token `.` para acceder a un miembro de un espacio de nombres o un tipo, como se muestran en los ejemplos siguientes:</span><span class="sxs-lookup"><span data-stu-id="9cb16-106">You use the `.` token to access a member of a namespace or a type, as the following examples demonstrate:</span></span>

- <span data-ttu-id="9cb16-107">Use `.` para acceder a un espacio de nombres anidado dentro de un espacio de nombres, como se muestra en el siguiente ejemplo de una [directiva `using`](../keywords/using-directive.md):</span><span class="sxs-lookup"><span data-stu-id="9cb16-107">Use `.` to access a nested namespace within a namespace, as the following example of a [`using` directive](../keywords/using-directive.md) shows:</span></span>

  [!code-csharp[nested namespaces](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#NestedNamespace)]

- <span data-ttu-id="9cb16-108">Use `.` para formar un *nombre completo* para tener acceso a un tipo dentro de un espacio de nombres, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9cb16-108">Use `.` to form a *qualified name* to access a type within a namespace, as the following code shows:</span></span>

  [!code-csharp[qualified name](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#QualifiedName)]

  <span data-ttu-id="9cb16-109">Utilice la [directiva `using`](../keywords/using-directive.md) para hacer que el uso de nombres completos sea opcional.</span><span class="sxs-lookup"><span data-stu-id="9cb16-109">Use the [`using` directive](../keywords/using-directive.md) to make the use of qualified names optional.</span></span>

- <span data-ttu-id="9cb16-110">Use `.` para tener acceso a los [miembros de tipo](../../programming-guide/classes-and-structs/index.md#members), que no son estáticos y, como se muestra en el código siguiente:</span><span class="sxs-lookup"><span data-stu-id="9cb16-110">Use `.` to access [type members](../../programming-guide/classes-and-structs/index.md#members), static and non-static, as the following code shows:</span></span>

  [!code-csharp-interactive[type members](~/samples/snippets/csharp/language-reference/operators/MemberAccessExamples.cs#TypeMemberAccess)]

<span data-ttu-id="9cb16-111">También puede usar `.` para invocar un [método de extensión](../../programming-guide/classes-and-structs/extension-methods.md).</span><span class="sxs-lookup"><span data-stu-id="9cb16-111">You can also use `.` to invoke an [extension method](../../programming-guide/classes-and-structs/extension-methods.md).</span></span>

## <a name="operator-overloadability"></a><span data-ttu-id="9cb16-112">Posibilidad de sobrecarga del operador</span><span class="sxs-lookup"><span data-stu-id="9cb16-112">Operator overloadability</span></span>

<span data-ttu-id="9cb16-113">El operador `.` no se puede sobrecargar.</span><span class="sxs-lookup"><span data-stu-id="9cb16-113">The operator `.` cannot be overloaded.</span></span>

## <a name="c-language-specification"></a><span data-ttu-id="9cb16-114">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="9cb16-114">C# language specification</span></span>

<span data-ttu-id="9cb16-115">Para obtener más información, vea la sección [Member access](~/_csharplang/spec/expressions.md#member-access) (Acceso a miembros) de la [especificación del lenguaje C#](../language-specification/index.md).</span><span class="sxs-lookup"><span data-stu-id="9cb16-115">For more information, see the [Member access](~/_csharplang/spec/expressions.md#member-access) section of the [C# language specification](../language-specification/index.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="9cb16-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="9cb16-116">See also</span></span>

- [<span data-ttu-id="9cb16-117">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="9cb16-117">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="9cb16-118">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="9cb16-118">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="9cb16-119">Operadores de C#</span><span class="sxs-lookup"><span data-stu-id="9cb16-119">C# Operators</span></span>](index.md)
- <span data-ttu-id="9cb16-120">[Operadores ?. y ?[]](null-conditional-operators.md)</span><span class="sxs-lookup"><span data-stu-id="9cb16-120">[?. and ?[] operators](null-conditional-operators.md)</span></span>