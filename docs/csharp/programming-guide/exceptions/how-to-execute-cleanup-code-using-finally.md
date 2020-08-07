---
title: 'Procedimiento Ejecutar código de limpieza mediante finally: Guía de programación de C#'
description: Aprenda a ejecutar código de limpieza mediante una instrucción "finally". Las instrucciones finally garantizan que cualquier limpieza necesaria de los objetos se produce inmediatamente.
ms.date: 07/20/2015
helpviewer_keywords:
- try/finally blocks [C#]
- exceptions [C#], try/finally block
- exception handling [C#], try/finally block
ms.assetid: 1b1e5aef-3f32-4a88-9d39-b5fffb33bdaf
ms.openlocfilehash: 148c1f9fba67659a07c667bb15619d6f3f7c3b2f
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/28/2020
ms.locfileid: "87302027"
---
# <a name="how-to-execute-cleanup-code-using-finally-c-programming-guide"></a><span data-ttu-id="cb5e3-104">Procedimiento Ejecutar código de limpieza mediante finally (Guía de programación de C#)</span><span class="sxs-lookup"><span data-stu-id="cb5e3-104">How to execute cleanup code using finally (C# Programming Guide)</span></span>
<span data-ttu-id="cb5e3-105">El propósito de una instrucción `finally` es asegurarse de que la limpieza necesaria de los objetos, por lo general objetos que contienen recursos externos, se produzca inmediatamente, incluso si se produce una excepción.</span><span class="sxs-lookup"><span data-stu-id="cb5e3-105">The purpose of a `finally` statement is to ensure that the necessary cleanup of objects, usually objects that are holding external resources, occurs immediately, even if an exception is thrown.</span></span> <span data-ttu-id="cb5e3-106">Un ejemplo de esta limpieza es llamar a <xref:System.IO.Stream.Close%2A> en un <xref:System.IO.FileStream> inmediatamente después de su uso en lugar de esperar a que el objeto sea recolectado por el Common Language Runtime, de esta forma:</span><span class="sxs-lookup"><span data-stu-id="cb5e3-106">One example of such cleanup is calling <xref:System.IO.Stream.Close%2A> on a <xref:System.IO.FileStream> immediately after use instead of waiting for the object to be garbage collected by the common language runtime, as follows:</span></span>  
  
 [!code-csharp[csProgGuideExceptions#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#16)]  
  
## <a name="example"></a><span data-ttu-id="cb5e3-107">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="cb5e3-107">Example</span></span>  
 <span data-ttu-id="cb5e3-108">Para activar el código anterior en una instrucción `try-catch-finally`, el código de limpieza se separa del código de trabajo, de esta forma.</span><span class="sxs-lookup"><span data-stu-id="cb5e3-108">To turn the previous code into a `try-catch-finally` statement, the cleanup code is separated from the working code, as follows.</span></span>  
  
 [!code-csharp[csProgGuideExceptions#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideExceptions/CS/Exceptions.cs#17)]  
  
 <span data-ttu-id="cb5e3-109">Dado que una excepción puede producirse en cualquier momento dentro del bloque `try` antes de la llamada a `OpenWrite()`, o que podría producirse un error en la propia llamada a `OpenWrite()`, no se garantiza que el archivo está abierto cuando se intenta cerrar.</span><span class="sxs-lookup"><span data-stu-id="cb5e3-109">Because an exception can occur at any time within the `try` block before the `OpenWrite()` call, or the `OpenWrite()` call itself could fail, we are not guaranteed that the file is open when we try to close it.</span></span> <span data-ttu-id="cb5e3-110">El bloque `finally` agrega una comprobación para asegurarse de que el objeto <xref:System.IO.FileStream> no es `null` antes de que pueda llamar al método <xref:System.IO.Stream.Close%2A>.</span><span class="sxs-lookup"><span data-stu-id="cb5e3-110">The `finally` block adds a check to make sure that the <xref:System.IO.FileStream> object is not `null` before you call the <xref:System.IO.Stream.Close%2A> method.</span></span> <span data-ttu-id="cb5e3-111">Sin la comprobación `null`, el bloque `finally` podría iniciar su propia excepción <xref:System.NullReferenceException>, pero debería evitarse generar excepciones en bloques `finally` si es posible.</span><span class="sxs-lookup"><span data-stu-id="cb5e3-111">Without the `null` check, the `finally` block could throw its own <xref:System.NullReferenceException>, but throwing exceptions in `finally` blocks should be avoided if it is possible.</span></span>  
  
 <span data-ttu-id="cb5e3-112">Una conexión de base de datos es otra buena candidata para cerrarse en un bloque `finally`.</span><span class="sxs-lookup"><span data-stu-id="cb5e3-112">A database connection is another good candidate for being closed in a `finally` block.</span></span> <span data-ttu-id="cb5e3-113">Dado que a veces se limita el número de conexiones permitido en un servidor de base de datos, se deben cerrar las conexiones de base de datos tan pronto como sea posible.</span><span class="sxs-lookup"><span data-stu-id="cb5e3-113">Because the number of connections allowed to a database server is sometimes limited, you should close database connections as quickly as possible.</span></span> <span data-ttu-id="cb5e3-114">Si se produce una excepción antes de poder cerrar la conexión, se trata de otro caso en el que usar el bloque `finally` es mejor que esperar a la recolección de elementos no utilizados.</span><span class="sxs-lookup"><span data-stu-id="cb5e3-114">If an exception is thrown before you can close your connection, this is another case where using the `finally` block is better than waiting for garbage collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cb5e3-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="cb5e3-115">See also</span></span>

- [<span data-ttu-id="cb5e3-116">Guía de programación de C#</span><span class="sxs-lookup"><span data-stu-id="cb5e3-116">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="cb5e3-117">Excepciones y control de excepciones</span><span class="sxs-lookup"><span data-stu-id="cb5e3-117">Exceptions and Exception Handling</span></span>](./index.md)
- [<span data-ttu-id="cb5e3-118">Control de excepciones</span><span class="sxs-lookup"><span data-stu-id="cb5e3-118">Exception Handling</span></span>](./exception-handling.md)
- [<span data-ttu-id="cb5e3-119">using (instrucción)</span><span class="sxs-lookup"><span data-stu-id="cb5e3-119">using Statement</span></span>](../../language-reference/keywords/using-statement.md)
- [<span data-ttu-id="cb5e3-120">try-catch</span><span class="sxs-lookup"><span data-stu-id="cb5e3-120">try-catch</span></span>](../../language-reference/keywords/try-catch.md)
- [<span data-ttu-id="cb5e3-121">try-finally</span><span class="sxs-lookup"><span data-stu-id="cb5e3-121">try-finally</span></span>](../../language-reference/keywords/try-finally.md)
- [<span data-ttu-id="cb5e3-122">try-catch-finally</span><span class="sxs-lookup"><span data-stu-id="cb5e3-122">try-catch-finally</span></span>](../../language-reference/keywords/try-catch-finally.md)
