---
title: "CorValidatorModuleType (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorValidatorModuleType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorValidatorModuleType
helpviewer_keywords:
- CorValidatorModuleType enumeration [.NET Framework metadata]
ms.assetid: 748f1ab2-fbcb-4f55-89ec-8d23d81ebc80
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 3367f6928b5d7378b2686185ee3e03d0279cc11d
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="3d4e5-102">CorValidatorModuleType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="3d4e5-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="3d4e5-103">Especifica el tipo de un módulo.</span><span class="sxs-lookup"><span data-stu-id="3d4e5-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3d4e5-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3d4e5-104">Syntax</span></span>  
  
```  
typedef enum  
{  
    ValidatorModuleTypeInvalid  = 0x0,  
    ValidatorModuleTypeMin      = 0x00000001,  
    ValidatorModuleTypePE       = 0x00000001,  
    ValidatorModuleTypeObj      = 0x00000002,  
    ValidatorModuleTypeEnc      = 0x00000003,  
    ValidatorModuleTypeIncr     = 0x00000004,  
    ValidatorModuleTypeMax      = 0x00000004  
} CorValidatorModuleType;  
```  
  
## <a name="members"></a><span data-ttu-id="3d4e5-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="3d4e5-105">Members</span></span>  
  
|<span data-ttu-id="3d4e5-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="3d4e5-106">Member</span></span>|<span data-ttu-id="3d4e5-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3d4e5-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="3d4e5-108">El módulo es un tipo no válido.</span><span class="sxs-lookup"><span data-stu-id="3d4e5-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="3d4e5-109">El valor mínimo de la `CorValidatorModuleType` enum.</span><span class="sxs-lookup"><span data-stu-id="3d4e5-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="3d4e5-110">El módulo es un archivo ejecutable portable (PE).</span><span class="sxs-lookup"><span data-stu-id="3d4e5-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="3d4e5-111">El módulo es un archivo .obj.</span><span class="sxs-lookup"><span data-stu-id="3d4e5-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="3d4e5-112">El módulo es una sesión del depurador de editar y continuar.</span><span class="sxs-lookup"><span data-stu-id="3d4e5-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="3d4e5-113">El módulo es aquel que se ha generado de forma incremental.</span><span class="sxs-lookup"><span data-stu-id="3d4e5-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="3d4e5-114">El valor máximo de la `CorValidatorModuleType` enum.</span><span class="sxs-lookup"><span data-stu-id="3d4e5-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3d4e5-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3d4e5-115">Requirements</span></span>  
 <span data-ttu-id="3d4e5-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3d4e5-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3d4e5-117">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="3d4e5-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3d4e5-118">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3d4e5-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3d4e5-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3d4e5-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d4e5-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="3d4e5-120">See Also</span></span>  
 [<span data-ttu-id="3d4e5-121">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="3d4e5-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
