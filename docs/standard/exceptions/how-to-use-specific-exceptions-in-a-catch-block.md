---
title: 'Cómo: Utilizar excepciones específicas en un bloque Catch'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try/catch blocks
- catch blocks
ms.assetid: 12af9ff3-8587-4f31-90cf-6c2244e0fdae
ms.openlocfilehash: bf4813e950b034cb807abebfe016c1e34487d594
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828028"
---
# <a name="how-to-use-specific-exceptions-in-a-catch-block"></a><span data-ttu-id="40c06-102">Cómo: Utilizar excepciones específicas en un bloque Catch</span><span class="sxs-lookup"><span data-stu-id="40c06-102">How to use specific exceptions in a catch block</span></span>

<span data-ttu-id="40c06-103">En general, en programación es recomendable detectar un tipo de excepción específico en lugar de usar una instrucción `catch` básica.</span><span class="sxs-lookup"><span data-stu-id="40c06-103">In general, it's good programming practice to catch a specific type of exception rather than use a basic `catch` statement.</span></span>

<span data-ttu-id="40c06-104">Cuando se produce una excepción, se pasa a la pila y cada bloque Catch tiene la oportunidad de controlarla.</span><span class="sxs-lookup"><span data-stu-id="40c06-104">When an exception occurs, it is passed up the stack and each catch block is given the opportunity to handle it.</span></span> <span data-ttu-id="40c06-105">El orden de las instrucciones Catch es importante.</span><span class="sxs-lookup"><span data-stu-id="40c06-105">The order of catch statements is important.</span></span> <span data-ttu-id="40c06-106">Ponga los bloques Catch dirigidos a excepciones específicas antes de un bloque Catch de excepción general o el compilador podría emitir un error.</span><span class="sxs-lookup"><span data-stu-id="40c06-106">Put catch blocks targeted to specific exceptions before a general exception catch block or the compiler might issue an error.</span></span> <span data-ttu-id="40c06-107">El bloque Catch adecuado se determina haciendo coincidir el tipo de la excepción con el nombre de la excepción especificada en el bloque Catch.</span><span class="sxs-lookup"><span data-stu-id="40c06-107">The proper catch block is determined by matching the type of the exception to the name of the exception specified in the catch block.</span></span> <span data-ttu-id="40c06-108">Si no hay ningún bloque Catch específico, la excepción se detecta mediante un bloque Catch general, si existe alguno.</span><span class="sxs-lookup"><span data-stu-id="40c06-108">If there is no specific catch block, the exception is caught by a general catch block, if one exists.</span></span>

<span data-ttu-id="40c06-109">En el siguiente ejemplo de código se usa un bloque `try`/`catch` para detectar una <xref:System.InvalidCastException>.</span><span class="sxs-lookup"><span data-stu-id="40c06-109">The following code example uses a `try`/`catch` block to catch an <xref:System.InvalidCastException>.</span></span> <span data-ttu-id="40c06-110">El ejemplo crea una clase denominada `Employee` con una propiedad única, el nivel de empleado (`Emlevel`).</span><span class="sxs-lookup"><span data-stu-id="40c06-110">The sample creates a class called `Employee` with a single property, employee level (`Emlevel`).</span></span> <span data-ttu-id="40c06-111">Un método, `PromoteEmployee`, toma un objeto e incrementa el nivel del empleado.</span><span class="sxs-lookup"><span data-stu-id="40c06-111">A method, `PromoteEmployee`, takes an object and increments the employee level.</span></span> <span data-ttu-id="40c06-112">Una <xref:System.InvalidCastException> se produce cuando una instancia de <xref:System.DateTime> se pasa al método `PromoteEmployee`.</span><span class="sxs-lookup"><span data-stu-id="40c06-112">An <xref:System.InvalidCastException> occurs when a <xref:System.DateTime> instance is passed to the `PromoteEmployee` method.</span></span>

[!code-cpp[CatchException#2](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception1.cpp#2)]
[!code-csharp[CatchException#2](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception1.cs#2)]
[!code-vb[CatchException#2](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception1.vb#2)]

## <a name="see-also"></a><span data-ttu-id="40c06-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="40c06-113">See also</span></span>

- [<span data-ttu-id="40c06-114">Excepciones</span><span class="sxs-lookup"><span data-stu-id="40c06-114">Exceptions</span></span>](index.md)
