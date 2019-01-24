---
title: AssemblyAttributesGoHereM
ms.date: 03/30/2017
api_name:
- AssemblyAttributesGoHereM
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- AssemblyAttributesGoHereM
helpviewer_keywords:
- AssemblyAttributesGoHereM type
- Alink API, AssemblyAttributesGoHereM type
ms.assetid: caaa8ba9-b4bb-4dd6-934d-57e436b2f3e5
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bbd5428039144fd38796ed6865c24a605f236ccd
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54733810"
---
# <a name="assemblyattributesgoherem"></a><span data-ttu-id="8de41-102">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="8de41-102">AssemblyAttributesGoHereM</span></span>
<span data-ttu-id="8de41-103">ALink lo utiliza como marcador de posición para almacenar información acerca de los atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="8de41-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8de41-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8de41-104">Syntax</span></span>  
  
```  
AssemblyAttributesGoHereM  
```  
  
## <a name="remarks"></a><span data-ttu-id="8de41-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8de41-105">Remarks</span></span>  
 <span data-ttu-id="8de41-106">Las referencias a este tipo se pueden incrustar en archivos .netmodules cuyos orígenes contengan atributos personalizados de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="8de41-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="8de41-107">Cuando se genera un manifiesto de ensamblado de uno o más .netmodules que contienen referencias a estos tipos, ALink utiliza la información adjunta a estas referencias para emitir atributos personalizados reales.</span><span class="sxs-lookup"><span data-stu-id="8de41-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="8de41-108">Como tal, nunca se crea una instancia de este tipo y las referencias a él se utilizan únicamente como parte del proceso de compilación, no sirven para ningún propósito en el ensamblado final.</span><span class="sxs-lookup"><span data-stu-id="8de41-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>  
  
 <span data-ttu-id="8de41-109">Las referencias a este tipo indican atributos personalizados que no están relacionados con la seguridad, pero que tienen diversos usos.</span><span class="sxs-lookup"><span data-stu-id="8de41-109">References to this type indicate custom attributes that are not security related but are multiple-use.</span></span>  
  
 <span data-ttu-id="8de41-110">Estos tipos se marcan como "internos" en .NET Framework y se encuentran en <xref:System.Runtime.CompilerServices>.</span><span class="sxs-lookup"><span data-stu-id="8de41-110">These types are marked "internal" within the .NET Framework, and are located in <xref:System.Runtime.CompilerServices>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8de41-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8de41-111">Requirements</span></span>  
 <span data-ttu-id="8de41-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="8de41-112">mscorlib.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8de41-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="8de41-113">See also</span></span>
- [<span data-ttu-id="8de41-114">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="8de41-114">AssemblyAttributesGoHere</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgohere.md)
- [<span data-ttu-id="8de41-115">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="8de41-115">AssemblyAttributesGoHereS</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheres.md)
- [<span data-ttu-id="8de41-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="8de41-116">AssemblyAttributesGoHereSM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheresm.md)
