---
title: Utilizar el bloque Try/Catch para detectar excepciones
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- exceptions, try/catch blocks
- try blocks
- try/catch blocks
- catch blocks
ms.assetid: a3ce6dfd-1f64-471b-8ad8-8cfaf406275d
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
- dotnetcore
ms.openlocfilehash: 192f762872b112ea261d22251175db6867229437
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
---
# <a name="how-to-use-the-trycatch-block-to-catch-exceptions"></a><span data-ttu-id="54faa-102">Cómo usar el bloque Try/Catch para detectar excepciones</span><span class="sxs-lookup"><span data-stu-id="54faa-102">How to use the try/catch block to catch exceptions</span></span>

<span data-ttu-id="54faa-103">Coloque las secciones del código que pueden iniciar excepciones en un bloque `try` y coloque el código que controla las excepciones en un bloque `catch`.</span><span class="sxs-lookup"><span data-stu-id="54faa-103">Place the sections of code that might throw exceptions in a `try` block and place code that handles exceptions in a `catch` block.</span></span> <span data-ttu-id="54faa-104">El bloque `catch` es una serie de instrucciones que comienzan con la palabra clave `catch`, seguido de un tipo de excepción y la acción que se debe realizar.</span><span class="sxs-lookup"><span data-stu-id="54faa-104">The `catch` block is a series of statements beginning with the keyword `catch`, followed by an exception type and an action to be taken.</span></span>

<span data-ttu-id="54faa-105">El siguiente ejemplo de código usa un bloque `try`/`catch` para detectar una posible excepción.</span><span class="sxs-lookup"><span data-stu-id="54faa-105">The following code example uses a `try`/`catch` block to catch a possible exception.</span></span> <span data-ttu-id="54faa-106">El método `Main` contiene un bloque `try` con una instrucción de <xref:System.IO.StreamReader> que abre un archivo de datos denominado `data.txt` y escribe una cadena del archivo.</span><span class="sxs-lookup"><span data-stu-id="54faa-106">The `Main` method contains a `try` block with a <xref:System.IO.StreamReader> statement that opens a data file called `data.txt` and writes a string from the file.</span></span> <span data-ttu-id="54faa-107">Después del bloque `try` aparece un bloque `catch` que detecta cualquier excepción que se produzca desde el bloque `try`.</span><span class="sxs-lookup"><span data-stu-id="54faa-107">Following the `try` block is a `catch` block that catches any exception that results from the `try` block.</span></span>

 [!code-cpp[CatchException#3](../../../samples/snippets/cpp/VS_Snippets_CLR/CatchException/CPP/catchexception2.cpp#3)]
 [!code-csharp[CatchException#3](../../../samples/snippets/csharp/VS_Snippets_CLR/CatchException/CS/catchexception2.cs#3)]
 [!code-vb[CatchException#3](../../../samples/snippets/visualbasic/VS_Snippets_CLR/CatchException/VB/catchexception2.vb#3)]  

<span data-ttu-id="54faa-108">Common Language Runtime detecta las excepciones que no se detectan mediante un bloque Catch.</span><span class="sxs-lookup"><span data-stu-id="54faa-108">The common language runtime catches exceptions that are not caught by a catch block.</span></span> <span data-ttu-id="54faa-109">Dependiendo de cómo esté configurado el runtime, aparece un cuadro de diálogo de depuración, el programa deja de ejecutarse y aparece un cuadro de diálogo con información sobre la excepción o bien se imprime un error en STDERR.</span><span class="sxs-lookup"><span data-stu-id="54faa-109">Depending on how the runtime is configured, a debug dialog box appears, or the program stops executing and a dialog box with exception information appears, or an error is printed out to STDERR.</span></span>

> [!NOTE] 
> <span data-ttu-id="54faa-110">Prácticamente cualquier línea de código puede originar una excepción, especialmente las excepciones iniciadas por Common Language Runtime, como <xref:System.OutOfMemoryException>.</span><span class="sxs-lookup"><span data-stu-id="54faa-110">Almost any line of code can cause an exception, particularly exceptions that are thrown by the common language runtime itself, such as <xref:System.OutOfMemoryException>.</span></span> <span data-ttu-id="54faa-111">La mayoría de las aplicaciones no tienen que tratar con estas excepciones, pero debe tener en cuenta esta posibilidad al escribir bibliotecas que puedan usar otros usuarios.</span><span class="sxs-lookup"><span data-stu-id="54faa-111">Most applications don't have to deal with these exceptions, but you should be aware of this possibility when writing libraries to be used by others.</span></span> <span data-ttu-id="54faa-112">Para obtener sugerencias sobre cuándo establecer el código en un bloque Try, consulte [Procedimientos recomendados para excepciones](best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="54faa-112">For suggestions on when to set code in a Try block, see [Best Practices for Exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="54faa-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="54faa-113">See Also</span></span>  
[<span data-ttu-id="54faa-114">Excepciones</span><span class="sxs-lookup"><span data-stu-id="54faa-114">Exceptions</span></span>](index.md)
