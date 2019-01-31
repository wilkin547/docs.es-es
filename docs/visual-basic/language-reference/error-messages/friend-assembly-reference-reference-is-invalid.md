---
title: La referencia de ensamblado de confianza <reference> no es válida
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: ff2cdbebe13f6224209ef8da62600c99348c911b
ms.sourcegitcommit: 14355b4b2fe5bcf874cac96d0a9e6376b567e4c7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/30/2019
ms.locfileid: "55286824"
---
# <a name="friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="0a3f1-102">Referencia de ensamblado de confianza \<referencia > no es válido</span><span class="sxs-lookup"><span data-stu-id="0a3f1-102">Friend assembly reference \<reference> is invalid</span></span>
<span data-ttu-id="0a3f1-103">Referencia de ensamblado de confianza \<referencia > no es válido.</span><span class="sxs-lookup"><span data-stu-id="0a3f1-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="0a3f1-104">Los ensamblados con signo de nombre seguro deben especificar una clave pública en las declaraciones InternalsVisibleTo.</span><span class="sxs-lookup"><span data-stu-id="0a3f1-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>  
  
 <span data-ttu-id="0a3f1-105">El nombre del ensamblado se pasa a la <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributo identifica un ensamblado con nombre seguro, pero no incluye un `PublicKey` atributo.</span><span class="sxs-lookup"><span data-stu-id="0a3f1-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>  
  
 <span data-ttu-id="0a3f1-106">**Identificador de error:** BC31535</span><span class="sxs-lookup"><span data-stu-id="0a3f1-106">**Error ID:** BC31535</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="0a3f1-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="0a3f1-107">To correct this error</span></span>  
  
1.  <span data-ttu-id="0a3f1-108">Determinar la clave pública para el ensamblado de confianza con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="0a3f1-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="0a3f1-109">Incluya la clave pública como parte del nombre de ensamblado pasado a la <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributo utilizando la `PublicKey` atributo.</span><span class="sxs-lookup"><span data-stu-id="0a3f1-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0a3f1-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a3f1-110">See also</span></span>
- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="0a3f1-111">Ensamblados de confianza</span><span class="sxs-lookup"><span data-stu-id="0a3f1-111">Friend Assemblies</span></span>](../../programming-guide/concepts/assemblies-gac/friend-assemblies.md)


