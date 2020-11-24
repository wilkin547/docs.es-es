---
title: Procedimiento Uso del bloque Try/Catch para detectar excepciones
description: Utilice el bloque Try para incluir instrucciones que puedan generar o producir una excepción. Coloque las instrucciones para controlar las excepciones en uno o varios bloques Catch.
ms.date: 02/06/2019
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
ms.openlocfilehash: cfe5b2b304cdb9efe7f0d91059fe1c279b4fa2dd
ms.sourcegitcommit: 965a5af7918acb0a3fd3baf342e15d511ef75188
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/18/2020
ms.locfileid: "94828015"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a><span data-ttu-id="c4a9c-104">Cómo usar el bloque Try/Catch para detectar excepciones</span><span class="sxs-lookup"><span data-stu-id="c4a9c-104">How to use the try/catch block to catch exceptions</span></span>

<span data-ttu-id="c4a9c-105">Coloque las instrucciones de código que podrían elevar o producir una excepción en un bloque `try`, y las que se usan para controlar la excepción o excepciones en uno o varios bloques `catch` debajo del bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="c4a9c-105">Place any code statements that might raise or throw an exception in a `try` block, and place statements used to handle the exception or exceptions in one or more `catch` blocks below the `try` block.</span></span> <span data-ttu-id="c4a9c-106">Cada bloque `catch` incluye el tipo de excepción y puede contener instrucciones adicionales necesarias para controlar ese tipo de excepción.</span><span class="sxs-lookup"><span data-stu-id="c4a9c-106">Each `catch` block includes the exception type and can contain additional statements needed to handle that exception type.</span></span>

<span data-ttu-id="c4a9c-107">En el ejemplo siguiente, un elemento <xref:System.IO.StreamReader> abre un archivo denominado *data.txt* y recupera una línea del archivo.</span><span class="sxs-lookup"><span data-stu-id="c4a9c-107">In the following example, a <xref:System.IO.StreamReader> opens a file called *data.txt* and retrieves a line from the file.</span></span> <span data-ttu-id="c4a9c-108">Como es posible que el código genere cualquiera de las tres excepciones, se coloca en un bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="c4a9c-108">Since the code might throw any of three exceptions, it's placed in a `try` block.</span></span> <span data-ttu-id="c4a9c-109">Tres bloques `catch` detectan las excepciones y las controlan mostrando los resultados en la consola.</span><span class="sxs-lookup"><span data-stu-id="c4a9c-109">Three `catch` blocks catch the exceptions and handle them by displaying the results to the console.</span></span>

[!code-csharp[CatchException#3](~/samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
[!code-vb[CatchException#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]

<span data-ttu-id="c4a9c-110">Common Language Runtime (CLR) detecta las excepciones no controladas por los bloques `catch`.</span><span class="sxs-lookup"><span data-stu-id="c4a9c-110">The Common Language Runtime (CLR) catches exceptions not handled by `catch` blocks.</span></span> <span data-ttu-id="c4a9c-111">Si CLR detecta una excepción, puede producirse uno de los resultados siguientes, en función de la configuración de CLR:</span><span class="sxs-lookup"><span data-stu-id="c4a9c-111">If an exception is caught by the CLR, one of the following results may occur depending on your CLR configuration:</span></span>

- <span data-ttu-id="c4a9c-112">Aparece un cuadro de diálogo **Depurar**.</span><span class="sxs-lookup"><span data-stu-id="c4a9c-112">A **Debug** dialog box appears.</span></span>
- <span data-ttu-id="c4a9c-113">El programa detiene la ejecución y aparece un cuadro de diálogo con información de la excepción.</span><span class="sxs-lookup"><span data-stu-id="c4a9c-113">The program stops execution and a dialog box with exception information appears.</span></span>
- <span data-ttu-id="c4a9c-114">Se imprime un error en el [flujo de salida de error estándar](xref:System.Console.Error).</span><span class="sxs-lookup"><span data-stu-id="c4a9c-114">An error prints out to the [standard error output stream](xref:System.Console.Error).</span></span>

> [!NOTE]
> <span data-ttu-id="c4a9c-115">La mayoría del código puede producir una excepción y algunas excepciones, como <xref:System.OutOfMemoryException>, las puede generar el propio CLR en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="c4a9c-115">Most code can throw an exception, and some exceptions, like <xref:System.OutOfMemoryException>, can be thrown by the CLR itself at any time.</span></span> <span data-ttu-id="c4a9c-116">Aunque no es obligatorio que las aplicaciones controlen estas excepciones, tenga en cuenta esta posibilidad al escribir bibliotecas que puedan usar otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="c4a9c-116">While applications aren't required to deal with these exceptions, be aware of the possibility when writing libraries to be used by others.</span></span> <span data-ttu-id="c4a9c-117">Para obtener sugerencias sobre cuándo establecer el código en un bloque `try`, vea [Procedimientos recomendados para excepciones](best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="c4a9c-117">For suggestions on when to set code in a `try` block, see [Best Practices for Exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="c4a9c-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="c4a9c-118">See also</span></span>

- [<span data-ttu-id="c4a9c-119">Excepciones</span><span class="sxs-lookup"><span data-stu-id="c4a9c-119">Exceptions</span></span>](index.md)
- [<span data-ttu-id="c4a9c-120">Control de errores de E/S en .NET</span><span class="sxs-lookup"><span data-stu-id="c4a9c-120">Handling I/O errors in .NET</span></span>](../io/handling-io-errors.md)
