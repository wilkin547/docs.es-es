---
title: Procedimiento para iniciar excepciones explícitamente
description: Aprenda a iniciar una excepción explícitamente en .NET mediante la instrucción throw de C# o la instrucción Throw de Visual Basic.
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
ms.openlocfilehash: 2dd939f9edd58ba91ea74df5d6930087849f0560
ms.sourcegitcommit: 7137e12f54c4e83a94ae43ec320f8cf59c1772ea
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 06/10/2020
ms.locfileid: "84662789"
---
# <a name="how-to-explicitly-throw-exceptions"></a><span data-ttu-id="dcb8b-103">Cómo iniciar excepciones explícitamente</span><span class="sxs-lookup"><span data-stu-id="dcb8b-103">How to explicitly throw exceptions</span></span>

<span data-ttu-id="dcb8b-104">Puede iniciar explícitamente una excepción mediante la instrucción [`throw`](../../csharp/language-reference/keywords/throw.md) de C# o la instrucción [`Throw`](../../visual-basic/language-reference/statements/throw-statement.md) de Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="dcb8b-104">You can explicitly throw an exception using the C# [`throw`](../../csharp/language-reference/keywords/throw.md) or the Visual Basic [`Throw`](../../visual-basic/language-reference/statements/throw-statement.md) statement.</span></span> <span data-ttu-id="dcb8b-105">También se puede iniciar una excepción detectada usando de nuevo la instrucción `throw`.</span><span class="sxs-lookup"><span data-stu-id="dcb8b-105">You can also throw a caught exception again using the `throw` statement.</span></span> <span data-ttu-id="dcb8b-106">En diseño de código, es recomendable agregar información a una excepción que se vuelve a iniciar para proporcionar más información durante la depuración.</span><span class="sxs-lookup"><span data-stu-id="dcb8b-106">It is good coding practice to add information to an exception that is re-thrown to provide more information when debugging.</span></span>

<span data-ttu-id="dcb8b-107">En el siguiente ejemplo de código se usa un bloque `try`/`catch` para detectar una posible <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="dcb8b-107">The following code example uses a `try`/`catch` block to catch a possible <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="dcb8b-108">Seguido del bloque `try` va un bloque `catch` que detecta <xref:System.IO.FileNotFoundException> y escribe un mensaje a la consola si no se encuentra el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="dcb8b-108">Following the `try` block is a `catch` block that catches the <xref:System.IO.FileNotFoundException> and writes a message to the console if the data file is not found.</span></span> <span data-ttu-id="dcb8b-109">La siguiente instrucción es `throw` que inicia un parámetro <xref:System.IO.FileNotFoundException> nuevo y agrega información de texto a la excepción.</span><span class="sxs-lookup"><span data-stu-id="dcb8b-109">The next statement is the `throw` statement that throws a new <xref:System.IO.FileNotFoundException> and adds text information to the exception.</span></span>

[!code-csharp[Exception.Throwing#1](~/samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](~/samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a><span data-ttu-id="dcb8b-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="dcb8b-110">See also</span></span>

- [<span data-ttu-id="dcb8b-111">Excepciones</span><span class="sxs-lookup"><span data-stu-id="dcb8b-111">Exceptions</span></span>](index.md)
