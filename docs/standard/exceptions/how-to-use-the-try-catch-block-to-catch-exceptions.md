---
title: Procedimiento Uso del bloque Try/Catch para detectar excepciones
ms.date: 02/06/2019
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
ms.openlocfilehash: 5a9218d394b76e897f4263708a10f1bc895ad4e1
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 01/07/2020
ms.locfileid: "75708471"
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a><span data-ttu-id="e0be2-102">Cómo usar el bloque Try/Catch para detectar excepciones</span><span class="sxs-lookup"><span data-stu-id="e0be2-102">How to use the try/catch block to catch exceptions</span></span>

<span data-ttu-id="e0be2-103">Coloque las instrucciones de código que podrían elevar o producir una excepción en un bloque `try`, y las que se usan para controlar la excepción o excepciones en uno o varios bloques `catch` debajo del bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="e0be2-103">Place any code statements that might raise or throw an exception in a `try` block, and place statements used to handle the exception or exceptions in one or more `catch` blocks below the `try` block.</span></span> <span data-ttu-id="e0be2-104">Cada bloque `catch` incluye el tipo de excepción y puede contener instrucciones adicionales necesarias para controlar ese tipo de excepción.</span><span class="sxs-lookup"><span data-stu-id="e0be2-104">Each `catch` block includes the exception type and can contain additional statements needed to handle that exception type.</span></span>

<span data-ttu-id="e0be2-105">En el ejemplo siguiente, un elemento <xref:System.IO.StreamReader> abre un archivo denominado *data.txt* y recupera una línea del archivo.</span><span class="sxs-lookup"><span data-stu-id="e0be2-105">In the following example, a <xref:System.IO.StreamReader> opens a file called *data.txt* and retrieves a line from the file.</span></span> <span data-ttu-id="e0be2-106">Como es posible que el código genere cualquiera de las tres excepciones, se coloca en un bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="e0be2-106">Since the code might throw any of three exceptions, it's placed in a `try` block.</span></span> <span data-ttu-id="e0be2-107">Tres bloques `catch` detectan las excepciones y las controlan mostrando los resultados en la consola.</span><span class="sxs-lookup"><span data-stu-id="e0be2-107">Three `catch` blocks catch the exceptions and handle them by displaying the results to the console.</span></span>

[!code-csharp[CatchException#3](~/samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
[!code-vb[CatchException#3](~/samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]

<span data-ttu-id="e0be2-108">Common Language Runtime (CLR) detecta las excepciones no controladas por los bloques `catch`.</span><span class="sxs-lookup"><span data-stu-id="e0be2-108">The Common Language Runtime (CLR) catches exceptions not handled by `catch` blocks.</span></span> <span data-ttu-id="e0be2-109">Si CLR detecta una excepción, puede producirse uno de los resultados siguientes, en función de la configuración de CLR:</span><span class="sxs-lookup"><span data-stu-id="e0be2-109">If an exception is caught by the CLR, one of the following results may occur depending on your CLR configuration:</span></span>

- <span data-ttu-id="e0be2-110">Aparece un cuadro de diálogo **Depurar**.</span><span class="sxs-lookup"><span data-stu-id="e0be2-110">A **Debug** dialog box appears.</span></span>
- <span data-ttu-id="e0be2-111">El programa detiene la ejecución y aparece un cuadro de diálogo con información de la excepción.</span><span class="sxs-lookup"><span data-stu-id="e0be2-111">The program stops execution and a dialog box with exception information appears.</span></span>
- <span data-ttu-id="e0be2-112">Se imprime un error en el [flujo de salida de error estándar](xref:System.Console.Error).</span><span class="sxs-lookup"><span data-stu-id="e0be2-112">An error prints out to the [standard error output stream](xref:System.Console.Error).</span></span>

> [!NOTE]
> <span data-ttu-id="e0be2-113">La mayoría del código puede producir una excepción y algunas excepciones, como <xref:System.OutOfMemoryException>, las puede generar el propio CLR en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="e0be2-113">Most code can throw an exception, and some exceptions, like <xref:System.OutOfMemoryException>, can be thrown by the CLR itself at any time.</span></span> <span data-ttu-id="e0be2-114">Aunque no es obligatorio que las aplicaciones controlen estas excepciones, tenga en cuenta esta posibilidad al escribir bibliotecas que puedan usar otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="e0be2-114">While applications aren't required to deal with these exceptions, be aware of the possibility when writing libraries to be used by others.</span></span> <span data-ttu-id="e0be2-115">Para obtener sugerencias sobre cuándo establecer el código en un bloque `try`, vea [Procedimientos recomendados para excepciones](best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="e0be2-115">For suggestions on when to set code in a `try` block, see [Best Practices for Exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="e0be2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e0be2-116">See also</span></span>

- [<span data-ttu-id="e0be2-117">Excepciones</span><span class="sxs-lookup"><span data-stu-id="e0be2-117">Exceptions</span></span>](index.md)
- [<span data-ttu-id="e0be2-118">Control de errores de E/S en .NET</span><span class="sxs-lookup"><span data-stu-id="e0be2-118">Handling I/O errors in .NET</span></span>](../io/handling-io-errors.md)
