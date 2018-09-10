---
title: 'Cómo: Iniciar excepciones explícitamente'
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
ms.openlocfilehash: a1a8658999f08d295e76afc9df6ec8acd146abe2
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "43863231"
---
# <a name="how-to-explicitly-throw-exceptions"></a><span data-ttu-id="eecdf-102">Cómo iniciar excepciones explícitamente</span><span class="sxs-lookup"><span data-stu-id="eecdf-102">How to explicitly throw exceptions</span></span>

<span data-ttu-id="eecdf-103">Puede iniciar explícitamente una excepción mediante la instrucción `throw`.</span><span class="sxs-lookup"><span data-stu-id="eecdf-103">You can explicitly throw an exception using the `throw` statement.</span></span> <span data-ttu-id="eecdf-104">También se puede iniciar una excepción detectada usando de nuevo la instrucción `throw`.</span><span class="sxs-lookup"><span data-stu-id="eecdf-104">You can also throw a caught exception again using the `throw` statement.</span></span> <span data-ttu-id="eecdf-105">En diseño de código, es recomendable agregar información a una excepción que se vuelve a iniciar para proporcionar más información durante la depuración.</span><span class="sxs-lookup"><span data-stu-id="eecdf-105">It is good coding practice to add information to an exception that is re-thrown to provide more information when debugging.</span></span>

<span data-ttu-id="eecdf-106">En el siguiente ejemplo de código se usa un bloque `try`/`catch` para detectar una posible <xref:System.IO.FileNotFoundException>.</span><span class="sxs-lookup"><span data-stu-id="eecdf-106">The following code example uses a `try`/`catch` block to catch a possible <xref:System.IO.FileNotFoundException>.</span></span> <span data-ttu-id="eecdf-107">Seguido del bloque `try` va un bloque `catch` que detecta <xref:System.IO.FileNotFoundException> y escribe un mensaje a la consola si no se encuentra el archivo de datos.</span><span class="sxs-lookup"><span data-stu-id="eecdf-107">Following the `try` block is a `catch` block that catches the <xref:System.IO.FileNotFoundException> and writes a message to the console if the data file is not found.</span></span> <span data-ttu-id="eecdf-108">La siguiente instrucción es `throw` que inicia un parámetro <xref:System.IO.FileNotFoundException> nuevo y agrega información de texto a la excepción.</span><span class="sxs-lookup"><span data-stu-id="eecdf-108">The next statement is the `throw` statement that throws a new <xref:System.IO.FileNotFoundException> and adds text information to the exception.</span></span>

[!code-csharp[Exception.Throwing#1](../../../samples/snippets/csharp/VS_Snippets_CLR/Exception.Throwing/CS/throw.cs#1)]
[!code-vb[Exception.Throwing#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/Exception.Throwing/VB/throw.vb#1)]  

## <a name="see-also"></a><span data-ttu-id="eecdf-109">Vea también</span><span class="sxs-lookup"><span data-stu-id="eecdf-109">See also</span></span>

- [<span data-ttu-id="eecdf-110">Excepciones</span><span class="sxs-lookup"><span data-stu-id="eecdf-110">Exceptions</span></span>](index.md)
