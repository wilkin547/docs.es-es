---
description: 'Más información sobre: enumeración Corvalidatormoduletype ('
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
ms.openlocfilehash: 13792c461660ddd8cfd530f5b34d642d806cdea4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707272"
---
# <a name="corvalidatormoduletype-enumeration"></a><span data-ttu-id="0e634-103">CorValidatorModuleType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="0e634-103">CorValidatorModuleType Enumeration</span></span>

<span data-ttu-id="0e634-104">Especifica el tipo de un módulo.</span><span class="sxs-lookup"><span data-stu-id="0e634-104">Specifies the type of a module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0e634-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0e634-105">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="0e634-106">Members</span><span class="sxs-lookup"><span data-stu-id="0e634-106">Members</span></span>  
  
|<span data-ttu-id="0e634-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="0e634-107">Member</span></span>|<span data-ttu-id="0e634-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="0e634-108">Description</span></span>|  
|------------|-----------------|  
|`ValidatorModuleTypeInvalid`|<span data-ttu-id="0e634-109">El módulo es un tipo no válido.</span><span class="sxs-lookup"><span data-stu-id="0e634-109">The module is an invalid type.</span></span>|  
|`ValidatorModuleTypeMin`|<span data-ttu-id="0e634-110">Valor mínimo de la `CorValidatorModuleType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="0e634-110">The minimum value of the `CorValidatorModuleType` enum.</span></span>|  
|`ValidatorModuleTypePE`|<span data-ttu-id="0e634-111">El módulo es un archivo ejecutable portable (PE).</span><span class="sxs-lookup"><span data-stu-id="0e634-111">The module is a portable executable (PE) file.</span></span>|  
|`ValidatorModuleTypeObj`|<span data-ttu-id="0e634-112">El módulo es un archivo. obj.</span><span class="sxs-lookup"><span data-stu-id="0e634-112">The module is a .obj file.</span></span>|  
|`ValidatorModuleTypeEnc`|<span data-ttu-id="0e634-113">El módulo es una sesión de depurador de edición y continuación.</span><span class="sxs-lookup"><span data-stu-id="0e634-113">The module is an edit-and-continue debugger session.</span></span>|  
|`ValidatorModuleTypeIncr`|<span data-ttu-id="0e634-114">El módulo es uno que se ha compilado incrementalmente.</span><span class="sxs-lookup"><span data-stu-id="0e634-114">The module is one that has been incrementally built.</span></span>|  
|`ValidatorModuleTypeMax`|<span data-ttu-id="0e634-115">Valor máximo de la `CorValidatorModuleType` enumeración.</span><span class="sxs-lookup"><span data-stu-id="0e634-115">The maximum value of the `CorValidatorModuleType` enum.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0e634-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0e634-116">Requirements</span></span>  

 <span data-ttu-id="0e634-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0e634-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0e634-118">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="0e634-118">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0e634-119">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0e634-119">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0e634-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0e634-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0e634-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="0e634-121">See also</span></span>

- [<span data-ttu-id="0e634-122">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="0e634-122">Metadata Enumerations</span></span>](metadata-enumerations.md)
