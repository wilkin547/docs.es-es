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
ms.openlocfilehash: c24ca43f35e237b6387e108563b1f9c9ed432242
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33402400"
---
# <a name="assemblyattributesgohere"></a><span data-ttu-id="bdf70-102">AssemblyAttributesGoHere</span><span class="sxs-lookup"><span data-stu-id="bdf70-102">AssemblyAttributesGoHere</span></span>
<span data-ttu-id="bdf70-103">ALink lo utiliza como marcador de posición para almacenar información acerca de los atributos personalizados.</span><span class="sxs-lookup"><span data-stu-id="bdf70-103">Used by ALink as a placeholder to store information about custom attributes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bdf70-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bdf70-104">Syntax</span></span>  
  
```  
AssemblyAttributesGoHere  
```  
  
## <a name="remarks"></a><span data-ttu-id="bdf70-105">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bdf70-105">Remarks</span></span>  
 <span data-ttu-id="bdf70-106">Las referencias a este tipo se pueden incrustar en archivos .netmodules cuyos orígenes contengan atributos personalizados de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="bdf70-106">References to this type might be embedded inside netmodules whose sources contain assembly custom attributes.</span></span> <span data-ttu-id="bdf70-107">Cuando se genera un manifiesto de ensamblado de uno o más .netmodules que contienen referencias a estos tipos, ALink utiliza la información adjunta a estas referencias para emitir atributos personalizados reales.</span><span class="sxs-lookup"><span data-stu-id="bdf70-107">When building an assembly manifest from one or more netmodules that contain references to these types, ALink uses information attached to these references to emit real custom attributes.</span></span> <span data-ttu-id="bdf70-108">Como tal, nunca se crea una instancia de este tipo y las referencias a él se utilizan únicamente como parte del proceso de compilación, no sirven para ningún propósito en el ensamblado final.</span><span class="sxs-lookup"><span data-stu-id="bdf70-108">As such, this type is never instantiated, and references to it are used only as part of the build process and serve no purpose in the final assembly.</span></span>  
  
 <span data-ttu-id="bdf70-109">Las referencias a este tipo indican atributos personalizados que no están relacionados con la seguridad y que no tienen diversos usos.</span><span class="sxs-lookup"><span data-stu-id="bdf70-109">References to this type indicate custom attributes that are not security related and are not multiple-use.</span></span>  
  
 <span data-ttu-id="bdf70-110">Estos tipos se marcan como "internos" en .NET Framework y se encuentran en <xref:System.Runtime.CompilerServices>.</span><span class="sxs-lookup"><span data-stu-id="bdf70-110">These types are marked "internal" within the .NET Framework, and are located in <xref:System.Runtime.CompilerServices>.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bdf70-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bdf70-111">Requirements</span></span>  
 <span data-ttu-id="bdf70-112">mscorlib.dll</span><span class="sxs-lookup"><span data-stu-id="bdf70-112">mscorlib.dll</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bdf70-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="bdf70-113">See Also</span></span>  
 [<span data-ttu-id="bdf70-114">AssemblyAttributesGoHereM</span><span class="sxs-lookup"><span data-stu-id="bdf70-114">AssemblyAttributesGoHereM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoherem.md)  
 [<span data-ttu-id="bdf70-115">AssemblyAttributesGoHereS</span><span class="sxs-lookup"><span data-stu-id="bdf70-115">AssemblyAttributesGoHereS</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheres.md)  
 [<span data-ttu-id="bdf70-116">AssemblyAttributesGoHereSM</span><span class="sxs-lookup"><span data-stu-id="bdf70-116">AssemblyAttributesGoHereSM</span></span>](../../../../docs/framework/unmanaged-api/alink/assemblyattributesgoheresm.md)
