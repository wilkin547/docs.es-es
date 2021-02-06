---
description: 'Más información sobre: clase AssemblyAttributesGoHereM'
title: Clase AssemblyAttributesGoHereM (System. Runtime. CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereM
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereM
helpviewer_keywords:
- AssemblyAttributesGoHereM type
- Alink API, AssemblyAttributesGoHereM type
ms.assetid: caaa8ba9-b4bb-4dd6-934d-57e436b2f3e5
topic_type:
- apiref
ms.openlocfilehash: 9afa72e5adbd539acaf8dfe45b446a61862df49e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638579"
---
# <a name="assemblyattributesgoherem-class"></a><span data-ttu-id="4fb34-103">Clase AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="4fb34-103">AssemblyAttributesGoHereM Class</span></span>

<span data-ttu-id="4fb34-104">ALink lo utiliza como marcador de posición para almacenar información acerca de los atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="4fb34-104">Used by ALink as a placeholder to store information about custom attributes.</span></span>

## <a name="syntax"></a><span data-ttu-id="4fb34-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4fb34-105">Syntax</span></span>

```csharp
internal sealed class AssemblyAttributesGoHereM
```

## <a name="remarks"></a><span data-ttu-id="4fb34-106">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4fb34-106">Remarks</span></span>

<span data-ttu-id="4fb34-107">Las referencias a este tipo se pueden incrustar en archivos .netmodules cuyos orígenes contengan atributos personalizados de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="4fb34-107">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="4fb34-108">Cuando se genera un manifiesto de ensamblado de uno o más .netmodules que contienen referencias a estos tipos, ALink utiliza la información adjunta a estas referencias para emitir atributos personalizados reales.</span><span class="sxs-lookup"><span data-stu-id="4fb34-108">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="4fb34-109">Como tal, nunca se crea una instancia de este tipo y las referencias a él se utilizan únicamente como parte del proceso de compilación, no sirven para ningún propósito en el ensamblado final.</span><span class="sxs-lookup"><span data-stu-id="4fb34-109">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>

<span data-ttu-id="4fb34-110">Las referencias a este tipo indican atributos personalizados que no están relacionados con la seguridad, pero que tienen diversos usos.</span><span class="sxs-lookup"><span data-stu-id="4fb34-110">References to this type indicate custom attributes that are not security related but are multiple-use.</span></span>

<span data-ttu-id="4fb34-111">Estos tipos se marcan como "Internal" dentro del .NET Framework y se encuentran en el <xref:System.Runtime.CompilerServices> espacio de nombres.</span><span class="sxs-lookup"><span data-stu-id="4fb34-111">These types are marked "internal" within the .NET Framework and are located in the <xref:System.Runtime.CompilerServices> namespace.</span></span>

## <a name="requirements"></a><span data-ttu-id="4fb34-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4fb34-112">Requirements</span></span>

<span data-ttu-id="4fb34-113">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="4fb34-113">mscorlib.dll</span></span>

## <a name="see-also"></a><span data-ttu-id="4fb34-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fb34-114">See also</span></span>

- [<span data-ttu-id="4fb34-115">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="4fb34-115">AssemblyAttributesGoHere</span></span>](assemblyattributesgohere.md)
- [<span data-ttu-id="4fb34-116">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="4fb34-116">AssemblyAttributesGoHereS</span></span>](assemblyattributesgoheres.md)
- [<span data-ttu-id="4fb34-117">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="4fb34-117">AssemblyAttributesGoHereSM</span></span>](assemblyattributesgoheresm.md)
