---
description: 'Más información acerca de: BC31535: la referencia de ensamblado de confianza <reference> no es válida'
title: La referencia de ensamblado de confianza <reference> no es válida
ms.date: 07/20/2015
f1_keywords:
- vbc31535
- bc31535
helpviewer_keywords:
- BC31535
ms.assetid: 6540c1d0-bb19-4051-a579-2e4f9094585e
ms.openlocfilehash: e3e08edede9bee4710c415a61592857229ea4f35
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99796202"
---
# <a name="bc31535-friend-assembly-reference-reference-is-invalid"></a><span data-ttu-id="0a6b7-103">BC31535: la referencia de ensamblado de confianza \<reference> no es válida</span><span class="sxs-lookup"><span data-stu-id="0a6b7-103">BC31535: Friend assembly reference \<reference> is invalid</span></span>

<span data-ttu-id="0a6b7-104">La referencia de ensamblado de confianza \<reference> no es válida.</span><span class="sxs-lookup"><span data-stu-id="0a6b7-104">Friend assembly reference \<reference> is invalid.</span></span> <span data-ttu-id="0a6b7-105">Los ensamblados con signo de nombre seguro deben especificar una clave pública en las declaraciones InternalsVisibleTo.</span><span class="sxs-lookup"><span data-stu-id="0a6b7-105">Strong-name signed assemblies must specify a public key in their InternalsVisibleTo declarations.</span></span>

 <span data-ttu-id="0a6b7-106">El nombre de ensamblado pasado al <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributos identifica un ensamblado con nombre seguro, pero no incluye un `PublicKey` atributo.</span><span class="sxs-lookup"><span data-stu-id="0a6b7-106">The assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor identifies a strong-named assembly, but it does not include a `PublicKey` attribute.</span></span>

 <span data-ttu-id="0a6b7-107">**Identificador de error:** BC31535</span><span class="sxs-lookup"><span data-stu-id="0a6b7-107">**Error ID:** BC31535</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="0a6b7-108">Para corregir este error</span><span class="sxs-lookup"><span data-stu-id="0a6b7-108">To correct this error</span></span>

1. <span data-ttu-id="0a6b7-109">Determine la clave pública del ensamblado de confianza con nombre seguro.</span><span class="sxs-lookup"><span data-stu-id="0a6b7-109">Determine the public key for the strong-named friend assembly.</span></span> <span data-ttu-id="0a6b7-110">Incluya la clave pública como parte del nombre del ensamblado pasado al <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> constructor de atributo mediante el `PublicKey` atributo.</span><span class="sxs-lookup"><span data-stu-id="0a6b7-110">Include the public key as part of the assembly name passed to the <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> attribute constructor by using the `PublicKey` attribute.</span></span>

## <a name="see-also"></a><span data-ttu-id="0a6b7-111">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a6b7-111">See also</span></span>

- <xref:System.Reflection.AssemblyName>
- [<span data-ttu-id="0a6b7-112">Ensamblados de confianza</span><span class="sxs-lookup"><span data-stu-id="0a6b7-112">Friend Assemblies</span></span>](../../../standard/assembly/friend.md)
