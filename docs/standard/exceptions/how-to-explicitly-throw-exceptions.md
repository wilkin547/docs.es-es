---
title: Procedimiento para iniciar excepciones explícitamente
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
helpviewer_keywords:
- exceptions, try/catch blocks
- FileNotFoundException class
- try/catch blocks
- exceptions, throwing
- implicitly throwing exceptions
ms.assetid: 72bdd157-caa9-4478-9ee3-cb4500b84528
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a71cefc0a6483dbbe6513a64d8111a07a2e5af42
ms.sourcegitcommit: 3094dcd17141b32a570a82ae3f62a331616e2c9c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/01/2019
ms.locfileid: "71696742"
---
# <a name="how-to-explicitly-throw-exceptions"></a><span data-ttu-id="5db0d-102">Cómo iniciar excepciones explícitamente</span><span class="sxs-lookup"><span data-stu-id="5db0d-102">How to explicitly throw exceptions</span></span>

<span data-ttu-id="5db0d-103">Puede iniciar explícitamente una excepción mediante la instrucción [`throw`](../../csharp/language-reference/keywords/throw.md) de C# o la instrucción [`Throw`](../../visual-basic/language-reference/statements/throw-statement.md) de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5db0d-103">You can explicitly throw an exception using the C# [`throw`](../../csharp/language-reference/keywords/throw.md) or the Visual Basic [`Throw`](../../visual-basic/language-reference/statements/throw-statement.md) statement.</span></span> <span data-ttu-id="5db0d-104">También se puede iniciar una excepción detectada usando de nuevo la instrucción `throw`.</span><span class="sxs-lookup"><span data-stu-id="5db0d-104">You can also throw a caught exception again using the `throw` statement.</span></span> <span data-ttu-id="5db0d-105">En diseño de código, es recomendable agregar información a una excepción que se vuelve a iniciar para proporcionar más información durante la depuración.</span><span class="sxs-lookup"><span data-stu-id="5db0d-105">It is good coding practice to add information to an exception that is re-thrown to provide more information when debugging.</span></span>

<span data-ttu-id="5db0d-106">En el siguiente ejemplo de código se usa un bloque `try`/`catch` para detectar una posible <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="5db0d-106">The following code example uses a `try`/`catch` block to catch a possible <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="5db0d-107">Seguido del bloque `try` va un bloque `catch` que detecta <xref:System.IO.FileNotFoundException> y escribe un mensaje a la consola si no se encuentra el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="5db0d-107">Following the `try` block is a `catch` block that catches the <xref:System.IO.FileNotFoundException> and writes a message to the console if the data file is not found.</span></span> <span data-ttu-id="5db0d-108">La siguiente instrucción es `throw` que inicia un parámetro <xref:System.IO.FileNotFoundException> nuevo y agrega información de texto a la excepción.</span><span class="sxs-lookup"><span data-stu-id="5db0d-108">The next statement is the `throw` statement that throws a new <xref:System.IO.FileNotFoundException> and adds text information to the exception.</span></span>

[!code-csharp[Exception.Throwing#1](~/samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a><span data-ttu-id="5db0d-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="5db0d-109">See also</span></span>

- [<span data-ttu-id="5db0d-110">Excepciones</span><span class="sxs-lookup"><span data-stu-id="5db0d-110">Exceptions</span></span>](index.md)
