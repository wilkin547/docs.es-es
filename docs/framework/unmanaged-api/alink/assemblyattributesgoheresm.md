---
title: Clase AssemblyAttributesGoHereSM (System.Runtime.CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereSM
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereSM
helpviewer_keywords:
- AssemblyAttributesGoHereSM type
- Alink API, AssemblyAttributesGoHereSM type
ms.assetid: 4cf9bf39-1527-49e0-a0e9-55e7a018bf66
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 01b156ed9c318e71a408ea10f2744911a85faedc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790343"
---
# <a name="assemblyattributesgoheresm-class"></a><span data-ttu-id="bb1e8-102">Clase AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="bb1e8-102">AssemblyAttributesGoHereSM Class</span></span>

<span data-ttu-id="bb1e8-103">ALink lo utiliza como marcador de posición para almacenar información acerca de los atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="bb1e8-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>

## <a name="syntax"></a><span data-ttu-id="bb1e8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb1e8-104">Syntax</span></span>

```csharp
internal sealed class AssemblyAttributesGoHereSM
```

## <a name="remarks"></a><span data-ttu-id="bb1e8-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bb1e8-105">Remarks</span></span>

<span data-ttu-id="bb1e8-106">Las referencias a este tipo se pueden incrustar en archivos .netmodules cuyos orígenes contengan atributos personalizados de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bb1e8-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="bb1e8-107">Cuando se genera un manifiesto de ensamblado de uno o más .netmodules que contienen referencias a estos tipos, ALink utiliza la información adjunta a estas referencias para emitir atributos personalizados reales.</span><span class="sxs-lookup"><span data-stu-id="bb1e8-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="bb1e8-108">Como tal, nunca se crea una instancia de este tipo y las referencias a él se utilizan únicamente como parte del proceso de compilación, no sirven para ningún propósito en el ensamblado final.</span><span class="sxs-lookup"><span data-stu-id="bb1e8-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>

<span data-ttu-id="bb1e8-109">Las referencias a este tipo indican atributos personalizados que están relacionados con la seguridad y que tienen diversos usos.</span><span class="sxs-lookup"><span data-stu-id="bb1e8-109">References to this type indicate custom attributes that are security related and multiple-use.</span></span>

<span data-ttu-id="bb1e8-110">Estos tipos se marcan como "internos" dentro de .NET Framework y se encuentran en el <xref:System.Runtime.CompilerServices> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="bb1e8-110">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span></span>

## <a name="requirements"></a><span data-ttu-id="bb1e8-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb1e8-111">Requirements</span></span>

<span data-ttu-id="bb1e8-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="bb1e8-112">mscorlib.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="bb1e8-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb1e8-113">See also</span></span>

- [<span data-ttu-id="bb1e8-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="bb1e8-114">AssemblyAttributesGoHere</span></span>](assemblyattributesgohere.md)
- [<span data-ttu-id="bb1e8-115">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="bb1e8-115">AssemblyAttributesGoHereM</span></span>](assemblyattributesgoherem.md)
- [<span data-ttu-id="bb1e8-116">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="bb1e8-116">AssemblyAttributesGoHereS</span></span>](assemblyattributesgoheres.md)
