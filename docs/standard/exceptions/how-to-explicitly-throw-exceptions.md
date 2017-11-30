---
title: "Cómo: Iniciar excepciones explícitamente"
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
helpviewer_keywords:
- exceptions, try/catch blocks
- FileNotFoundException class
- try/catch blocks
- exceptions, throwing
- implicitly throwing exceptions
ms.assetid: 72bdd157-caa9-4478-9ee3-cb4500b84528
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: c3fce332263dac3f9906d33fe3bd2590050b86f8
ms.sourcegitcommit: bbde43da655ae7bea1977f7af7345eb87bd7fd5f
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/21/2017
---
# <a name="how-to-explicitly-throw-exceptions"></a><span data-ttu-id="bb4b9-102">Cómo iniciar excepciones explícitamente</span><span class="sxs-lookup"><span data-stu-id="bb4b9-102">How to explicitly throw exceptions</span></span>

<span data-ttu-id="bb4b9-103">Puede iniciar explícitamente una excepción mediante la instrucción `throw`.</span><span class="sxs-lookup"><span data-stu-id="bb4b9-103">You can explicitly throw an exception using the `throw` statement.</span></span> <span data-ttu-id="bb4b9-104">También se puede iniciar una excepción detectada usando de nuevo la instrucción `throw`.</span><span class="sxs-lookup"><span data-stu-id="bb4b9-104">You can also throw a caught exception again using the `throw` statement.</span></span> <span data-ttu-id="bb4b9-105">En diseño de código, es recomendable agregar información a una excepción que se vuelve a iniciar para proporcionar más información durante la depuración.</span><span class="sxs-lookup"><span data-stu-id="bb4b9-105">It is good coding practice to add information to an exception that is re-thrown to provide more information when debugging.</span></span>

<span data-ttu-id="bb4b9-106">En el siguiente ejemplo de código se usa un bloque `try`/`catch` para detectar una posible <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="bb4b9-106">The following code example uses a `try`/`catch` block to catch a possible <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="bb4b9-107">Seguido del bloque `try` va un bloque `catch` que detecta <xref:System.IO.FileNotFoundException> y escribe un mensaje a la consola si no se encuentra el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="bb4b9-107">Following the `try` block is a `catch` block that catches the <xref:System.IO.FileNotFoundException> and writes a message to the console if the data file is not found.</span></span> <span data-ttu-id="bb4b9-108">La siguiente instrucción es `throw` que inicia un parámetro <xref:System.IO.FileNotFoundException> nuevo y agrega información de texto a la excepción.</span><span class="sxs-lookup"><span data-stu-id="bb4b9-108">The next statement is the `throw` statement that throws a new <xref:System.IO.FileNotFoundException> and adds text information to the exception.</span></span>

[!code-csharp[Exception.Throwing#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a><span data-ttu-id="bb4b9-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb4b9-109">See Also</span></span>  
[<span data-ttu-id="bb4b9-110">Excepciones</span><span class="sxs-lookup"><span data-stu-id="bb4b9-110">Exceptions</span></span>](index.md)
