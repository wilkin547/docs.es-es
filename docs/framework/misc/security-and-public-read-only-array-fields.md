---
title: Seguridad y campos de matriz públicos de sólo lectura
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 03f3ce51eaab9e08d5f05932d9360adc4fd2110f
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54560998"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="bb4f7-102">Seguridad y campos de matriz públicos de sólo lectura</span><span class="sxs-lookup"><span data-stu-id="bb4f7-102">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="bb4f7-103">Nunca use los campos de matriz públicos de sólo lectura de las bibliotecas administradas para definir el comportamiento de límite o la seguridad de las aplicaciones porque se pueden modificar los campos de matriz públicos de sólo lectura.</span><span class="sxs-lookup"><span data-stu-id="bb4f7-103">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="bb4f7-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bb4f7-104">Remarks</span></span>  
 <span data-ttu-id="bb4f7-105">Algunas clases de .NET framework incluyen campos públicos de sólo lectura que contienen los parámetros de los límites específicos de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="bb4f7-105">Some .NET framework classes include read-only public fields that contain platform-specific boundary parameters.</span></span>  <span data-ttu-id="bb4f7-106">Por ejemplo, el <xref:System.IO.Path.InvalidPathChars> campo es una matriz que describe los caracteres que no se permiten en una cadena de ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="bb4f7-106">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span>  <span data-ttu-id="bb4f7-107">Existen muchos campos similares a lo largo de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bb4f7-107">Many similar fields are present throughout the .NET Framework.</span></span>  
  
 <span data-ttu-id="bb4f7-108">Al igual que los valores de campos públicos de sólo lectura <xref:System.IO.Path.InvalidPathChars> puede modificarse mediante el código o el código que comparte el dominio de aplicación de su código.</span><span class="sxs-lookup"><span data-stu-id="bb4f7-108">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="bb4f7-109">No debe usar los campos de matriz públicos de sólo lectura similar al siguiente para definir el comportamiento de límite de sus aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="bb4f7-109">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="bb4f7-110">Si lo hace, código malintencionado puede modificar las definiciones de límite y usar el código de manera inesperada.</span><span class="sxs-lookup"><span data-stu-id="bb4f7-110">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="bb4f7-111">En la versión 2.0 y versiones posteriores de .NET Framework, debe usar los métodos que devuelven una nueva matriz en lugar de usar campos de matriz públicos.</span><span class="sxs-lookup"><span data-stu-id="bb4f7-111">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="bb4f7-112">Por ejemplo, en lugar de usar el <xref:System.IO.Path.InvalidPathChars> campo, debe usar el <xref:System.IO.Path.GetInvalidPathChars%2A> método.</span><span class="sxs-lookup"><span data-stu-id="bb4f7-112">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="bb4f7-113">Tenga en cuenta que los tipos de .NET Framework no utilizan los campos públicos para definir tipos de límites internamente.</span><span class="sxs-lookup"><span data-stu-id="bb4f7-113">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="bb4f7-114">En su lugar, .NET Framework utiliza campos privados separados.</span><span class="sxs-lookup"><span data-stu-id="bb4f7-114">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="bb4f7-115">Cambiar los valores de estos campos públicos no modifica el comportamiento de los tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="bb4f7-115">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb4f7-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb4f7-116">See also</span></span>
- [<span data-ttu-id="bb4f7-117">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="bb4f7-117">Secure Coding Guidelines</span></span>](../../../docs/standard/security/secure-coding-guidelines.md)
