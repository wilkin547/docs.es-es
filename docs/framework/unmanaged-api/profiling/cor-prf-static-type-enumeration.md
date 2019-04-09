---
title: COR_PRF_STATIC_TYPE (Enumeración)
ms.date: 03/30/2017
api_name:
- COR_PRF_STATIC_TYPE
api_location:
- mscorwks.dll
api_type:
- COM
f1_keywords:
- COR_PRF_STATIC_TYPE
helpviewer_keywords:
- COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 310915ce84819a2a5a2d5e1f22356b61c16e7ec7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59190501"
---
# <a name="corprfstatictype-enumeration"></a><span data-ttu-id="e6bda-102">COR_PRF_STATIC_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="e6bda-102">COR_PRF_STATIC_TYPE Enumeration</span></span>
<span data-ttu-id="e6bda-103">Indica si un campo es estático y, si lo es, la calidad estática que se aplica al campo.</span><span class="sxs-lookup"><span data-stu-id="e6bda-103">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="e6bda-104">Estos valores se pueden combinar con la operación OR bit a bit para indicar que el campo tiene varias calidades estáticas diferentes.</span><span class="sxs-lookup"><span data-stu-id="e6bda-104">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e6bda-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6bda-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="e6bda-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="e6bda-106">Members</span></span>  
  
|<span data-ttu-id="e6bda-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="e6bda-107">Member</span></span>|<span data-ttu-id="e6bda-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6bda-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="e6bda-109">El campo no es estático.</span><span class="sxs-lookup"><span data-stu-id="e6bda-109">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="e6bda-110">El campo es estático del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="e6bda-110">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="e6bda-111">El campo es de subproceso estático.</span><span class="sxs-lookup"><span data-stu-id="e6bda-111">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="e6bda-112">El campo es estático de contexto.</span><span class="sxs-lookup"><span data-stu-id="e6bda-112">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="e6bda-113">El campo es la dirección virtual relativa (RVA)-static.</span><span class="sxs-lookup"><span data-stu-id="e6bda-113">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e6bda-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6bda-114">Requirements</span></span>  
 <span data-ttu-id="e6bda-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6bda-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6bda-116">**Encabezado**: CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="e6bda-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="e6bda-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e6bda-117">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e6bda-118">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e6bda-118">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e6bda-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="e6bda-119">See also</span></span>

- [<span data-ttu-id="e6bda-120">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="e6bda-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
