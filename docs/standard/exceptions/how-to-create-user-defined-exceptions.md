---
title: 'Cómo: Crear excepciones definidas por el usuario'
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- user-defined exceptions
- exceptions, examples
- exceptions, user-defined
ms.assetid: 25819a5a-f915-4fc8-b924-a76915674e04
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 90bf9d6dbfebf8f7c1aa22e5844cf4e30b89b8d6
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-create-user-defined-exceptions"></a><span data-ttu-id="59548-102">Cómo crear excepciones definidas por el usuario</span><span class="sxs-lookup"><span data-stu-id="59548-102">How to create user-defined exceptions</span></span>

<span data-ttu-id="59548-103">.NET proporciona una jerarquía de clases de excepciones derivadas en última instancia de la clase base <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="59548-103">.NET provides a hierarchy of exception classes ultimately derived from the base class <xref:System.Exception>.</span></span> <span data-ttu-id="59548-104">Pero si ninguna de las excepciones predefinidas satisface sus necesidades, puede crear sus propias clases de excepciones derivadas de la clase <xref:System.Exception>.</span><span class="sxs-lookup"><span data-stu-id="59548-104">However, if none of the predefined exceptions meets your needs, you can create your own exception classes by deriving from the <xref:System.Exception> class.</span></span>

<span data-ttu-id="59548-105">Al crear sus propias excepciones, termine el nombre de clase de la excepción definida por el usuario con la palabra "Exception" e implemente los tres constructores comunes, como se muestra en el ejemplo siguiente.</span><span class="sxs-lookup"><span data-stu-id="59548-105">When creating your own exceptions, end the class name of the user-defined exception with the word "Exception," and implement the three common constructors, as shown in the following example.</span></span> <span data-ttu-id="59548-106">En el ejemplo se define una nueva clase de excepción denominada `EmployeeListNotFoundException`.</span><span class="sxs-lookup"><span data-stu-id="59548-106">The example defines a new exception class named `EmployeeListNotFoundException`.</span></span> <span data-ttu-id="59548-107">La clase se deriva de <xref:System.Exception> e incluye tres constructores.</span><span class="sxs-lookup"><span data-stu-id="59548-107">The class is derived from <xref:System.Exception> and includes three constructors.</span></span>

[!code-cpp[dg_exceptionDesign#14](../../../samples/snippets/cpp/VS_Snippets_CLR/dg_exceptionDesign/cpp/example2.cpp#14)]
[!code-csharp[dg_exceptionDesign#14](../../../samples/snippets/csharp/VS_Snippets_CLR/dg_exceptionDesign/cs/example2.cs#14)]
[!code-vb[dg_exceptionDesign#14](../../../samples/snippets/visualbasic/VS_Snippets_CLR/dg_exceptionDesign/vb/example2.vb#14)]  

> [!NOTE]
> <span data-ttu-id="59548-108">En situaciones en que use la comunicación remota, debe asegurarse de que los metadatos de todas las excepciones definidas por el usuario estén disponibles en el servidor (destinatario) y en el cliente (el objeto proxy o autor de la llamada).</span><span class="sxs-lookup"><span data-stu-id="59548-108">In situations where you are using remoting, you must ensure that the metadata for any user-defined exceptions is available at the server (callee) and to the client (the proxy object or caller).</span></span> <span data-ttu-id="59548-109">Para obtener más información, consulte [Procedimientos recomendados para excepciones](best-practices-for-exceptions.md).</span><span class="sxs-lookup"><span data-stu-id="59548-109">For more information, see [Best practices for exceptions](best-practices-for-exceptions.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="59548-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="59548-110">See Also</span></span>  
[<span data-ttu-id="59548-111">Excepciones</span><span class="sxs-lookup"><span data-stu-id="59548-111">Exceptions</span></span>](index.md)
