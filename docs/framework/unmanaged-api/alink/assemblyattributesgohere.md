---
title: AssemblyAttributesGoHere
ms.date: 03/30/2017
api_name:
- AssemblyAttributesGoHere
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyAttributesGoHere
helpviewer_keywords:
- AssemblyAttributesGoHere type
- Alink API, AssemblyAttributesGoHere type
ms.assetid: 7b26fcb6-94f4-4f09-933e-b33efe451f4f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: cde96ed9089416fa5febe55e49b4109cfeb11f40
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54722145"
---
# <a name="assemblyattributesgohere"></a><span data-ttu-id="bb6ef-102">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="bb6ef-102">AssemblyAttributesGoHere</span></span>
<span data-ttu-id="bb6ef-103">ALink lo utiliza como marcador de posición para almacenar información acerca de los atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="bb6ef-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bb6ef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bb6ef-104">Syntax</span></span>  
  
```  
AssemblyAttributesGoHere  
```  
  
## <a name="remarks"></a><span data-ttu-id="bb6ef-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bb6ef-105">Remarks</span></span>  
 <span data-ttu-id="bb6ef-106">Las referencias a este tipo se pueden incrustar en archivos .netmodules cuyos orígenes contengan atributos personalizados de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bb6ef-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="bb6ef-107">Cuando se genera un manifiesto de ensamblado de uno o más .netmodules que contienen referencias a estos tipos, ALink utiliza la información adjunta a estas referencias para emitir atributos personalizados reales.</span><span class="sxs-lookup"><span data-stu-id="bb6ef-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="bb6ef-108">Como tal, nunca se crea una instancia de este tipo y las referencias a él se utilizan únicamente como parte del proceso de compilación, no sirven para ningún propósito en el ensamblado final.</span><span class="sxs-lookup"><span data-stu-id="bb6ef-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>  
  
 <span data-ttu-id="bb6ef-109">Las referencias a este tipo indican atributos personalizados que no están relacionados con la seguridad y que no tienen diversos usos.</span><span class="sxs-lookup"><span data-stu-id="bb6ef-109">References to this type indicate custom attributes that are not security related and are not multiple-use.</span></span>  
  
 <span data-ttu-id="bb6ef-110">Estos tipos se marcan como "internos" en .NET Framework y se encuentran en <xref:System.Runtime.CompilerServices>.</span><span class="sxs-lookup"><span data-stu-id="bb6ef-110">These types are marked "internal" within the .NET Framework, and are located in <xref:System.Runtime.CompilerServices>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bb6ef-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bb6ef-111">Requirements</span></span>  
 <span data-ttu-id="bb6ef-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="bb6ef-112">mscorlib.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bb6ef-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="bb6ef-113">See also</span></span>
- [<span data-ttu-id="bb6ef-114">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="bb6ef-114">AssemblyAttributesGoHereM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoherem.md)
- [<span data-ttu-id="bb6ef-115">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="bb6ef-115">AssemblyAttributesGoHereS</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheres.md)
- [<span data-ttu-id="bb6ef-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="bb6ef-116">AssemblyAttributesGoHereSM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheresm.md)
