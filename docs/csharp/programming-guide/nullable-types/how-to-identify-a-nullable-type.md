---
title: 'Identificación de tipos de valor que admiten un valor NULL: Guía de programación de C#'
ms.custom: seodec18
description: Obtenga información sobre cómo determinar si un tipo es un tipo de valor que admite un valor NULL o una instancia es de un tipo de valor que admite un valor NULL
ms.date: 09/26/2019
helpviewer_keywords:
- nullable value types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: 15b1ffedf57648955ee5a004514841a5d140292b
ms.sourcegitcommit: da2dd2772fcf32b44eb18b1cbe8affd17b1753c9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/27/2019
ms.locfileid: "71392610"
---
# <a name="how-to-identify-a-nullable-value-type-c-programming-guide"></a><span data-ttu-id="70920-103">Identificación de tipos de valor que admiten un valor NULL (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="70920-103">How to: identify a nullable value type (C# Programming Guide)</span></span>

<span data-ttu-id="70920-104">El ejemplo siguiente muestra cómo determinar si una instancia <xref:System.Type?displayProperty=nameWithType> representa un tipo de valor genérico cerrado que admite un valor NULL, es decir, el tipo <xref:System.Nullable%601?displayProperty=nameWithType> con un parámetro de tipo especificado `T`:</span><span class="sxs-lookup"><span data-stu-id="70920-104">The following example shows how to determine whether a <xref:System.Type?displayProperty=nameWithType> instance represents a closed generic nullable value type, that is, the <xref:System.Nullable%601?displayProperty=nameWithType> type with a specified type parameter `T`:</span></span>

[!code-csharp-interactive[whether Type is nullable](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#1)]

<span data-ttu-id="70920-105">Como se muestra en el ejemplo, se usa el operador [typeof](../../language-reference/operators/type-testing-and-cast.md#typeof-operator) para crear un objeto <xref:System.Type?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="70920-105">As the example shows, you use the [typeof](../../language-reference/operators/type-testing-and-cast.md#typeof-operator) operator to create a <xref:System.Type?displayProperty=nameWithType> object.</span></span>

<span data-ttu-id="70920-106">Si quiere determinar si una instancia es de un tipo de valor que admite un valor NULL, no use el método <xref:System.Object.GetType%2A?displayProperty=nameWithType> para obtener una instancia de <xref:System.Type> para probarla con el código anterior.</span><span class="sxs-lookup"><span data-stu-id="70920-106">If you want to determine whether an instance is of a nullable value type, don't use the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method to get a <xref:System.Type> instance to be tested with the preceding code.</span></span> <span data-ttu-id="70920-107">Cuando se llama al método <xref:System.Object.GetType%2A?displayProperty=nameWithType> en una instancia de un tipo de valor que admite un valor NULL, [se aplica la conversión boxing](using-nullable-types.md#boxing-and-unboxing) a la instancia para convertirla en <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="70920-107">When you call the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method on an instance of a nullable value type, the instance is [boxed](using-nullable-types.md#boxing-and-unboxing) to <xref:System.Object>.</span></span> <span data-ttu-id="70920-108">Como la conversión boxing de una instancia que no es NULL de un tipo de valor que admite un valor NULL equivale la conversión boxing de un valor del tipo subyacente, <xref:System.Object.GetType%2A> devuelve un objeto <xref:System.Type> que representa el tipo de valor subyacente que admite un valor NULL:</span><span class="sxs-lookup"><span data-stu-id="70920-108">As boxing of a non-null instance of a nullable value type is equivalent to boxing of a value of the underlying type, <xref:System.Object.GetType%2A> returns a <xref:System.Type> object that represents the underlying type of a nullable value type:</span></span>

[!code-csharp-interactive[GetType example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#2)]

<span data-ttu-id="70920-109">No use el operador [is](../../language-reference/keywords/is.md) para determinar si una instancia es de un tipo de valor que admite un valor NULL.</span><span class="sxs-lookup"><span data-stu-id="70920-109">Don't use the [is](../../language-reference/keywords/is.md) operator to determine whether an instance is of a nullable value type.</span></span> <span data-ttu-id="70920-110">Como se muestra en el ejemplo siguiente, no se pueden distinguir los tipos de instancias de un tipo de valor que admite un valor NULL y su tipo subyacente mediante el operador `is`:</span><span class="sxs-lookup"><span data-stu-id="70920-110">As the following example shows, you cannot distinguish types of instances of a nullable value type and its underlying type with using the `is` operator:</span></span>

[!code-csharp-interactive[is operator example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#3)]

<span data-ttu-id="70920-111">Se puede usar el código que se presenta en el ejemplo siguiente para determinar si una instancia es de un tipo de valor que admite un valor NULL:</span><span class="sxs-lookup"><span data-stu-id="70920-111">You can use the code presented in the following example to determine whether an instance is of a nullable value type:</span></span>

[!code-csharp-interactive[whether an instance is of a nullable type](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#4)]

## <a name="see-also"></a><span data-ttu-id="70920-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="70920-112">See also</span></span>

- [<span data-ttu-id="70920-113">Tipos de valores que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="70920-113">Nullable value types</span></span>](index.md)
- [<span data-ttu-id="70920-114">Uso de tipos que admiten un valor NULL</span><span class="sxs-lookup"><span data-stu-id="70920-114">Using nullable value types</span></span>](using-nullable-types.md)
- <xref:System.Nullable.GetUnderlyingType%2A>
