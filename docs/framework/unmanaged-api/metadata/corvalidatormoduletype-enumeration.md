---
title: CorValidatorModuleType (Enumeración)
ms.date: 03/30/2017
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
ms.openlocfilehash: a8dc09ee9f0f0fd79060bb86c599ab40a285153b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74448762"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="1d690-102">CorValidatorModuleType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="1d690-102">CorValidatorModuleType Enumeration</span></span>
<span data-ttu-id="1d690-103">Especifica el tipo de un módulo.</span><span class="sxs-lookup"><span data-stu-id="1d690-103">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1d690-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1d690-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="1d690-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="1d690-105">Members</span></span>  
  
|<span data-ttu-id="1d690-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="1d690-106">Member</span></span>|<span data-ttu-id="1d690-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="1d690-107">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="1d690-108">El módulo es un tipo no válido.</span><span class="sxs-lookup"><span data-stu-id="1d690-108">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="1d690-109">Valor mínimo de la enumeración `CorValidatorModuleType`.</span><span class="sxs-lookup"><span data-stu-id="1d690-109">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="1d690-110">El módulo es un archivo ejecutable portable (PE).</span><span class="sxs-lookup"><span data-stu-id="1d690-110">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="1d690-111">El módulo es un archivo. obj.</span><span class="sxs-lookup"><span data-stu-id="1d690-111">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="1d690-112">El módulo es una sesión de depurador de edición y continuación.</span><span class="sxs-lookup"><span data-stu-id="1d690-112">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="1d690-113">El módulo es uno que se ha compilado incrementalmente.</span><span class="sxs-lookup"><span data-stu-id="1d690-113">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="1d690-114">Valor máximo de la enumeración `CorValidatorModuleType`.</span><span class="sxs-lookup"><span data-stu-id="1d690-114">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1d690-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1d690-115">Requirements</span></span>  
 <span data-ttu-id="1d690-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1d690-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1d690-117">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1d690-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1d690-118">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="1d690-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1d690-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1d690-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1d690-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="1d690-120">See also</span></span>

- [<span data-ttu-id="1d690-121">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="1d690-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
