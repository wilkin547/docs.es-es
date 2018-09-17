---
title: 'Cómo: Utilizar bloques Finally'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- exceptions, finally blocks
- try/catch blocks
- finally blocks
- ArgumentOutOfRangeException class
ms.assetid: 4b9c0137-04af-4468-91d1-b9014df8ddd2
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 213ab53c68a37ac0ba5f337a1d6fc32bfe6f8989
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/16/2018
ms.locfileid: "45618226"
---
# <a name="how-to-use-finally-blocks"></a><span data-ttu-id="30621-102">Cómo usar bloques Finally</span><span class="sxs-lookup"><span data-stu-id="30621-102">How to use finally blocks</span></span>

<span data-ttu-id="30621-103">Cuando se produce una excepción, se detiene la ejecución y se proporciona el control al controlador de excepciones adecuado.</span><span class="sxs-lookup"><span data-stu-id="30621-103">When an exception occurs, execution stops and control is given to the appropriate exception handler.</span></span> <span data-ttu-id="30621-104">A menudo, esto significa que se omiten líneas de código que esperaba que se ejecuten.</span><span class="sxs-lookup"><span data-stu-id="30621-104">This often means that lines of code you expect to be executed are bypassed.</span></span> <span data-ttu-id="30621-105">Se debe realizar alguna limpieza de recursos, como cerrar un archivo, aunque se inicie una excepción.</span><span class="sxs-lookup"><span data-stu-id="30621-105">Some resource cleanup, such as closing a file, needs to be done even if an exception is thrown.</span></span> <span data-ttu-id="30621-106">Para ello, puede usar un bloque `finally`.</span><span class="sxs-lookup"><span data-stu-id="30621-106">To do this, you can use a `finally` block.</span></span> <span data-ttu-id="30621-107">Un bloque `finally` siempre se ejecuta, independientemente de si se inicia una excepción.</span><span class="sxs-lookup"><span data-stu-id="30621-107">A `finally` block always executes, regardless of whether an exception is thrown.</span></span>

<span data-ttu-id="30621-108">En el siguiente ejemplo de código se usa un bloque `try`/`catch` para detectar una <xref:System.ArgumentOutOfRangeException>.</span><span class="sxs-lookup"><span data-stu-id="30621-108">The following code example uses a `try`/`catch` block to catch an <xref:System.ArgumentOutOfRangeException>.</span></span> <span data-ttu-id="30621-109">El método `Main` crea dos matrices e intenta copiar una en la otra.</span><span class="sxs-lookup"><span data-stu-id="30621-109">The `Main` method creates two arrays and attempts to copy one to the other.</span></span> <span data-ttu-id="30621-110">La acción genera un <xref:System.ArgumentOutOfRangeException> y el error se escribe en la consola.</span><span class="sxs-lookup"><span data-stu-id="30621-110">The action generates an <xref:System.ArgumentOutOfRangeException> and the error is written to the console.</span></span> <span data-ttu-id="30621-111">Este bloque `finally` se ejecuta independientemente del resultado de la acción de copia.</span><span class="sxs-lookup"><span data-stu-id="30621-111">The `finally` block executes regardless of the outcome of the copy action.</span></span>

[!code-cpp[CodeTryCatchFinallyExample#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CPP/source2.cpp#3)]
[!code-csharp[CodeTryCatchFinallyExample#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CodeTryCatchFinallyExample/CS/source2.cs#3)]
[!code-vb[CodeTryCatchFinallyExample#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CodeTryCatchFinallyExample/VB/source2.vb#3)]  

## <a name="see-also"></a><span data-ttu-id="30621-112">Vea también</span><span class="sxs-lookup"><span data-stu-id="30621-112">See also</span></span>

- [<span data-ttu-id="30621-113">Excepciones</span><span class="sxs-lookup"><span data-stu-id="30621-113">Exceptions</span></span>](index.md)
