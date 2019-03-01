---
title: AssemblyAttributesGoHereS
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereS
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereS
helpviewer_keywords:
- AssemblyAttributesGoHereS type
- Alink API, AssemblyAttributesGoHereS type
ms.assetid: 4e817f35-a2bc-4403-9e6f-f731e6b9fe23
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 74447f52c75ae22e513c6f07950630d37bad191a
ms.sourcegitcommit: 40364ded04fa6cdcb2b6beca7f68412e2e12f633
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/28/2019
ms.locfileid: "56969835"
---
# <a name="assemblyattributesgoheres"></a><span data-ttu-id="ebde2-102">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="ebde2-102">AssemblyAttributesGoHereS</span></span>

<span data-ttu-id="ebde2-103">ALink lo utiliza como marcador de posición para almacenar información acerca de los atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="ebde2-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>

## <a name="syntax"></a><span data-ttu-id="ebde2-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ebde2-104">Syntax</span></span>

```
internal sealed class AssemblyAttributesGoHereS
```

## <a name="remarks"></a><span data-ttu-id="ebde2-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ebde2-105">Remarks</span></span>

<span data-ttu-id="ebde2-106">Las referencias a este tipo se pueden incrustar en archivos .netmodules cuyos orígenes contengan atributos personalizados de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="ebde2-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="ebde2-107">Cuando se genera un manifiesto de ensamblado de uno o más .netmodules que contienen referencias a estos tipos, ALink utiliza la información adjunta a estas referencias para emitir atributos personalizados reales.</span><span class="sxs-lookup"><span data-stu-id="ebde2-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="ebde2-108">Como tal, nunca se crea una instancia de este tipo y las referencias a él se utilizan únicamente como parte del proceso de compilación, no sirven para ningún propósito en el ensamblado final.</span><span class="sxs-lookup"><span data-stu-id="ebde2-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>

<span data-ttu-id="ebde2-109">Las referencias a este tipo indican atributos personalizados que están relacionados con la seguridad y que no tienen diversos usos.</span><span class="sxs-lookup"><span data-stu-id="ebde2-109">References to this type indicate custom attributes that are security related and are not multiple-use.</span></span>

<span data-ttu-id="ebde2-110">Estos tipos se marcan como "internos" dentro de .NET Framework y se encuentran en el <xref:System.Runtime.CompilerServices> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="ebde2-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span></span>

## <a name="requirements"></a><span data-ttu-id="ebde2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ebde2-111">Requirements</span></span>

<span data-ttu-id="ebde2-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="ebde2-112">mscorlib.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="ebde2-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="ebde2-113">See also</span></span>

- [<span data-ttu-id="ebde2-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="ebde2-114">AssemblyAttributesGoHere</span></span>](assemblyattributesgohere.md)
- [<span data-ttu-id="ebde2-115">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="ebde2-115">AssemblyAttributesGoHereM</span></span>](assemblyattributesgoherem.md)
- [<span data-ttu-id="ebde2-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="ebde2-116">AssemblyAttributesGoHereSM</span></span>](assemblyattributesgoheresm.md)
