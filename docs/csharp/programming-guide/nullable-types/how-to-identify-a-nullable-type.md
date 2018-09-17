---
title: 'Cómo: Identificar tipos que aceptan valores NULL (Guía de programación de C#)'
description: Obtenga información sobre cómo determinar si un tipo es un tipo que acepta valores NULL o una instancia es de un tipo que acepta valores NULL.
ms.date: 08/06/2018
helpviewer_keywords:
- nullable types [C#], identifying
ms.assetid: d4b67ee2-66e8-40c1-ae9d-545d32c71387
ms.openlocfilehash: c65f80974154d81b5ddf239b617eeeda68434e09
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/17/2018
ms.locfileid: "45624954"
---
# <a name="how-to-identify-a-nullable-type-c-programming-guide"></a><span data-ttu-id="cc442-103">Cómo: Identificar tipos que aceptan valores NULL (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="cc442-103">How to: Identify a nullable type (C# Programming Guide)</span></span>

<span data-ttu-id="cc442-104">En el ejemplo siguiente se muestra cómo determinar si una instancia de <xref:System.Type?displayProperty=nameWithType> representa un tipo que acepta valores NULL:</span><span class="sxs-lookup"><span data-stu-id="cc442-104">The following example shows how to determine whether a <xref:System.Type?displayProperty=nameWithType> instance represents a nullable type:</span></span>

[!code-csharp-interactive[whether Type is nullable](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#1)]

<span data-ttu-id="cc442-105">Como se muestra en el ejemplo, se usa el operador [typeof](../../language-reference/keywords/typeof.md) para crear un objeto <xref:System.Type?displayProperty=nameWithType>.</span><span class="sxs-lookup"><span data-stu-id="cc442-105">As the example shows, you use the [typeof](../../language-reference/keywords/typeof.md) operator to create a <xref:System.Type?displayProperty=nameWithType> object.</span></span>  
  
<span data-ttu-id="cc442-106">Si quiere determinar si una instancia es de un tipo que acepta valores NULL, no use el método <xref:System.Object.GetType%2A?displayProperty=nameWithType> para obtener una instancia de <xref:System.Type> para probarla con el código anterior.</span><span class="sxs-lookup"><span data-stu-id="cc442-106">If you want to determine whether an instance is of a nullable type, don't use the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method to get a <xref:System.Type> instance to be tested with the preceding code.</span></span> <span data-ttu-id="cc442-107">Cuando se llama al método <xref:System.Object.GetType%2A?displayProperty=nameWithType> en una instancia de un tipo que acepta valores NULL, [se aplica la conversión boxing](using-nullable-types.md#boxing-and-unboxing) a la instancia para convertirla en <xref:System.Object>.</span><span class="sxs-lookup"><span data-stu-id="cc442-107">When you call the <xref:System.Object.GetType%2A?displayProperty=nameWithType> method on an instance of a nullable type, the instance is [boxed](using-nullable-types.md#boxing-and-unboxing) to <xref:System.Object>.</span></span> <span data-ttu-id="cc442-108">Como la conversión boxing de una instancia que no es NULL de un tipo que acepta valores NULL equivale la conversión boxing de un valor del tipo subyacente, <xref:System.Object.GetType%2A> devuelve un objeto <xref:System.Type> que representa el tipo subyacente de un tipo que acepta valores NULL:</span><span class="sxs-lookup"><span data-stu-id="cc442-108">As boxing of a non-null instance of a nullable type is equivalent to boxing of a value of the underlying type, <xref:System.Object.GetType%2A> returns a <xref:System.Type> object that represents the underlying type of a nullable type:</span></span>

[!code-csharp-interactive[GetType example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#2)]

<span data-ttu-id="cc442-109">No use el operador [is](../../language-reference/keywords/is.md) para determinar si una instancia es de un tipo que acepta valores NULL.</span><span class="sxs-lookup"><span data-stu-id="cc442-109">Don't use the [is](../../language-reference/keywords/is.md) operator to determine whether an instance is of a nullable type.</span></span> <span data-ttu-id="cc442-110">Como se muestra en el ejemplo siguiente, no se pueden distinguir los tipos de instancias de un tipo que acepta valores NULL y su tipo subyacente mediante el operador `is`:</span><span class="sxs-lookup"><span data-stu-id="cc442-110">As the following example shows, you cannot distinguish types of instances of a nullable type and its underlying type with using the `is` operator:</span></span>

[!code-csharp-interactive[is operator example](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#3)]

<span data-ttu-id="cc442-111">Se puede usar el código que se presenta en el ejemplo siguiente para determinar si una instancia es de un tipo que acepta valores NULL:</span><span class="sxs-lookup"><span data-stu-id="cc442-111">You can use the code presented in the following example to determine whether an instance is of a nullable type:</span></span>

[!code-csharp-interactive[whether an instance is of a nullable type](../../../../samples/snippets/csharp/programming-guide/nullable-types/IdentifyNullableType.cs#4)]
  
## <a name="see-also"></a><span data-ttu-id="cc442-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc442-112">See Also</span></span>

- <span data-ttu-id="cc442-113">[Nullable types](index.md) (Tipos que aceptan valores NULL [Guía de programación de C#])</span><span class="sxs-lookup"><span data-stu-id="cc442-113">[Nullable types](index.md)</span></span>  
- [<span data-ttu-id="cc442-114">Uso de tipos que aceptan valores NULL</span><span class="sxs-lookup"><span data-stu-id="cc442-114">Using nullable types</span></span>](using-nullable-types.md)  
- <xref:System.Nullable.GetUnderlyingType%2A>  
