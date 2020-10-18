---
title: La referencia de ensamblado de confianza <reference> no es válida
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: a42dd99ffaa06dce4823ce5d022fac02ae99c6bd
ms.sourcegitcommit: ff5a4eb5cffbcac9521bc44a907a118cd7e8638d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/17/2020
ms.locfileid: "92160716"
---
# <a name="bc31535-friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="dab74-102">BC31535: la referencia de ensamblado de confianza \<reference> no es válida</span><span class="sxs-lookup"><span data-stu-id="dab74-102">BC31535: Friend assembly reference \<reference> is invalid</span></span>

<span data-ttu-id="dab74-103">La referencia de ensamblado de confianza \<reference> no es válida.</span><span class="sxs-lookup"><span data-stu-id="dab74-103">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="dab74-104">Los ensamblados con signo de nombre seguro deben especificar una clave pública en las declaraciones InternalsVisibleTo.</span><span class="sxs-lookup"><span data-stu-id="dab74-104">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>

 <span data-ttu-id="dab74-105">El nombre de ensamblado pasado al <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributos identifica un ensamblado con nombre seguro, pero no incluye un `PublicKey` atributo.</span><span class="sxs-lookup"><span data-stu-id="dab74-105">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>

 <span data-ttu-id="dab74-106">**Identificador de error:** BC31535</span><span class="sxs-lookup"><span data-stu-id="dab74-106">**Error ID:** BC31535</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="dab74-107">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="dab74-107">To correct this error</span></span>

1. <span data-ttu-id="dab74-108">Determine la clave pública del ensamblado de confianza con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="dab74-108">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="dab74-109">Incluya la clave pública como parte del nombre del ensamblado pasado al <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributo mediante el `PublicKey` atributo.</span><span class="sxs-lookup"><span data-stu-id="dab74-109">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>

## <a name="see-also"></a><span data-ttu-id="dab74-110">Vea también</span><span class="sxs-lookup"><span data-stu-id="dab74-110">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="dab74-111">Ensamblados de confianza</span><span class="sxs-lookup"><span data-stu-id="dab74-111">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
