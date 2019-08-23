---
title: Seguridad y campos de matriz públicos de sólo lectura
ms.date: 03/30/2017
helpviewer_keywords:
- security [.NET Framework], public read-only array fields
ms.assetid: 3df28dee-2a9f-40ff-9852-bfdbe59c27f3
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 3d36009fa4fc7b9299708768fe34a75f1fde6797
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69910736"
---
# <a name="security-and-public-read-only-array-fields"></a><span data-ttu-id="3764d-102">Seguridad y campos de matriz públicos de sólo lectura</span><span class="sxs-lookup"><span data-stu-id="3764d-102">Security and Public Read-only Array Fields</span></span>
<span data-ttu-id="3764d-103">Nunca use campos de matriz pública de solo lectura de las bibliotecas administradas para definir el comportamiento del límite o la seguridad de las aplicaciones, ya que se pueden modificar los campos de matriz pública de solo lectura.</span><span class="sxs-lookup"><span data-stu-id="3764d-103">Never use read-only public array fields from managed libraries to define the boundary behavior or security of your applications because read-only public array fields can be modified.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3764d-104">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3764d-104">Remarks</span></span>  
 <span data-ttu-id="3764d-105">Algunas clases de .NET Framework incluyen campos públicos de solo lectura que contienen parámetros de límite específicos de la plataforma.</span><span class="sxs-lookup"><span data-stu-id="3764d-105">Some .NET framework classes include read-only public fields that contain platform-specific boundary parameters.</span></span>  <span data-ttu-id="3764d-106">Por ejemplo, el <xref:System.IO.Path.InvalidPathChars> campo es una matriz que describe los caracteres que no están permitidos en una cadena de ruta de acceso de archivo.</span><span class="sxs-lookup"><span data-stu-id="3764d-106">For example, the <xref:System.IO.Path.InvalidPathChars> field is an array that describes the characters that are not allowed in a file path string.</span></span>  <span data-ttu-id="3764d-107">Muchos campos similares están presentes en el .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3764d-107">Many similar fields are present throughout the .NET Framework.</span></span>  
  
 <span data-ttu-id="3764d-108">Los valores de los campos públicos de solo lectura <xref:System.IO.Path.InvalidPathChars> como pueden ser modificados por el código o el código que comparte el dominio de aplicación del código.</span><span class="sxs-lookup"><span data-stu-id="3764d-108">The values of public read-only fields like <xref:System.IO.Path.InvalidPathChars> can be modified by your code or code that shares your code’s application domain.</span></span>  <span data-ttu-id="3764d-109">No debe utilizar campos de matriz pública de solo lectura como este para definir el comportamiento de los límites de las aplicaciones.</span><span class="sxs-lookup"><span data-stu-id="3764d-109">You should not use read-only public array fields like this to define the boundary behavior of your applications.</span></span>  <span data-ttu-id="3764d-110">Si lo hace, el código malintencionado puede modificar las definiciones de límite y usar el código de maneras inesperadas.</span><span class="sxs-lookup"><span data-stu-id="3764d-110">If you do, malicious code can alter the boundary definitions and use your code in unexpected ways.</span></span>  
  
 <span data-ttu-id="3764d-111">En la versión 2,0 y posteriores de la .NET Framework, debe utilizar métodos que devuelvan una nueva matriz en lugar de usar campos de matriz públicos.</span><span class="sxs-lookup"><span data-stu-id="3764d-111">In version 2.0 and later of the .NET Framework, you should use methods that return a new array instead of using public array fields.</span></span>  <span data-ttu-id="3764d-112">Por ejemplo, en lugar de utilizar el <xref:System.IO.Path.InvalidPathChars> campo, debe utilizar el <xref:System.IO.Path.GetInvalidPathChars%2A> método.</span><span class="sxs-lookup"><span data-stu-id="3764d-112">For example, instead of using the <xref:System.IO.Path.InvalidPathChars> field, you should use the <xref:System.IO.Path.GetInvalidPathChars%2A> method.</span></span>  
  
 <span data-ttu-id="3764d-113">Tenga en cuenta que los tipos de .NET Framework no utilizan los campos públicos para definir tipos de límites internamente.</span><span class="sxs-lookup"><span data-stu-id="3764d-113">Note that the .NET Framework types do not use the public fields to define boundary types internally.</span></span>  <span data-ttu-id="3764d-114">En su lugar, el .NET Framework utiliza campos privados independientes.</span><span class="sxs-lookup"><span data-stu-id="3764d-114">Instead, the .NET Framework uses separate private fields.</span></span>  <span data-ttu-id="3764d-115">El cambio de los valores de estos campos públicos no altera el comportamiento de los tipos de .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="3764d-115">Changing the values of these public fields does not alter the behavior of .NET Framework types.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3764d-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="3764d-116">See also</span></span>

- [<span data-ttu-id="3764d-117">Instrucciones de codificación segura</span><span class="sxs-lookup"><span data-stu-id="3764d-117">Secure Coding Guidelines</span></span>](../../standard/security/secure-coding-guidelines.md)
