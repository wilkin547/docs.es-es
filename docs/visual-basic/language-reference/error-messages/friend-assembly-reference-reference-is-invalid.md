---
title: "Referencia de ensamblado de confianza &lt;referencia&gt; no es válido"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords: BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 39ae94e309ee8d18e6b5317445b7e4b7f6a42af9
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="friend-assembly-reference-ltreferencegt-is-invalid"></a><span data-ttu-id="83b9e-102">Referencia de ensamblado de confianza &lt;referencia&gt; no es válido</span><span class="sxs-lookup"><span data-stu-id="83b9e-102">Friend assembly reference &lt;reference&gt; is invalid</span></span>
<span data-ttu-id="83b9e-103">Referencia de ensamblado de confianza \<referencia > no es válido.</span><span class="sxs-lookup"><span data-stu-id="83b9e-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="83b9e-104">Los ensamblados con signo de nombre seguro deben especificar una clave pública en las declaraciones InternalsVisibleTo.</span><span class="sxs-lookup"><span data-stu-id="83b9e-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="83b9e-105">El nombre del ensamblado se pasa a la <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributo identifica un ensamblado con nombre seguro, pero no incluye un `PublicKey` atributo.</span><span class="sxs-lookup"><span data-stu-id="83b9e-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="83b9e-106">**Id. de error:** BC31535</span><span class="sxs-lookup"><span data-stu-id="83b9e-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="83b9e-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="83b9e-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="83b9e-108">Determinar la clave pública para el ensamblado con nombre seguro friend.</span><span class="sxs-lookup"><span data-stu-id="83b9e-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="83b9e-109">Incluya la clave pública como parte del nombre del ensamblado que se pasa a la <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributo mediante el uso de la `PublicKey` atributo.</span><span class="sxs-lookup"><span data-stu-id="83b9e-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="83b9e-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="83b9e-110">See Also</span></span>  
 <xref:System.Reflection.AssemblyName>  
 [<span data-ttu-id="83b9e-111">Ensamblados de confianza</span><span class="sxs-lookup"><span data-stu-id="83b9e-111">Friend Assemblies</span></span>](http://msdn.microsoft.com/library/df0c70ea-2c2a-4bdc-9526-df951ad2d055)  
 [<span data-ttu-id="83b9e-112">Crear ensamblados de confianza firmados</span><span class="sxs-lookup"><span data-stu-id="83b9e-112">How to: Create Signed Friend Assemblies</span></span>](http://msdn.microsoft.com/library/f5542300-58b4-4e1c-b809-8df11e95e69b)
