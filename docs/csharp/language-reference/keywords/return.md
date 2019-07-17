---
title: 'Instrucción return: Referencia de C#'
ms.custom: seodec18
ms.date: 07/20/2015
f1_keywords:
- return_CSharpKeyword
- return
helpviewer_keywords:
- return statement [C#]
- return keyword [C#]
ms.assetid: 6da6e152-5b58-4448-8f3f-470dd0617ecd
ms.openlocfilehash: a845ce257bf7f0cf0e64d6815b2278f6cec946e7
ms.sourcegitcommit: d6e27023aeaffc4b5a3cb4b88685018d6284ada4
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/09/2019
ms.locfileid: "67661613"
---
# <a name="return-c-reference"></a><span data-ttu-id="16e99-102">return (Referencia de C#)</span><span class="sxs-lookup"><span data-stu-id="16e99-102">return (C# Reference)</span></span>

<span data-ttu-id="16e99-103">La instrucción `return` termina la ejecución del método en el que aparece y devuelve el control al método de llamada.</span><span class="sxs-lookup"><span data-stu-id="16e99-103">The `return` statement terminates execution of the method in which it appears and returns control to the calling method.</span></span> <span data-ttu-id="16e99-104">También puede devolver un valor opcional.</span><span class="sxs-lookup"><span data-stu-id="16e99-104">It can also return an optional value.</span></span> <span data-ttu-id="16e99-105">Si el método es del tipo `void`, la instrucción `return` se puede omitir.</span><span class="sxs-lookup"><span data-stu-id="16e99-105">If the method is a `void` type, the `return` statement can be omitted.</span></span>

 <span data-ttu-id="16e99-106">Si la instrucción return está incluida en un bloque `try`, el bloque `finally`, si existe, se ejecutará antes de que el control se devuelva al método de llamada.</span><span class="sxs-lookup"><span data-stu-id="16e99-106">If the return statement is inside a `try` block, the `finally` block, if one exists, will be executed before control returns to the calling method.</span></span>

## <a name="example"></a><span data-ttu-id="16e99-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="16e99-107">Example</span></span>

 <span data-ttu-id="16e99-108">En el siguiente ejemplo, el método `CalculateArea()` devuelve la variable local `area` como un valor de tipo `double`.</span><span class="sxs-lookup"><span data-stu-id="16e99-108">In the following example, the method `CalculateArea()` returns the local variable `area` as a `double` value.</span></span>

[!code-csharp[csrefKeywordsJump#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsJump/CS/csrefKeywordsJump.cs#6)]  

## <a name="c-language-specification"></a><span data-ttu-id="16e99-109">Especificación del lenguaje C#</span><span class="sxs-lookup"><span data-stu-id="16e99-109">C# language specification</span></span>

[!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]

## <a name="see-also"></a><span data-ttu-id="16e99-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="16e99-110">See also</span></span>

- [<span data-ttu-id="16e99-111">Referencia de C#</span><span class="sxs-lookup"><span data-stu-id="16e99-111">C# Reference</span></span>](../index.md)
- [<span data-ttu-id="16e99-112">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="16e99-112">C# Programming Guide</span></span>](../../programming-guide/index.md)
- [<span data-ttu-id="16e99-113">Palabras clave de C#</span><span class="sxs-lookup"><span data-stu-id="16e99-113">C# Keywords</span></span>](index.md)
- [<span data-ttu-id="16e99-114">return (instrucción)</span><span class="sxs-lookup"><span data-stu-id="16e99-114">return Statement</span></span>](/cpp/cpp/return-statement-cpp)
