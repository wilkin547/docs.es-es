---
title: "COR_PRF_STATIC_TYPE (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: COR_PRF_STATIC_TYPE
api_location: mscorwks.dll
api_type: COM
f1_keywords: COR_PRF_STATIC_TYPE
helpviewer_keywords: COR_PRF_STATIC_TYPE enumeration [.NET Framework profiling]
ms.assetid: 441d7809-5b65-41a5-ba64-2910a8008315
topic_type: apiref
caps.latest.revision: "10"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 446967cc157962a1ec4a87193bbf84b1a356efa6
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corprfstatictype-enumeration"></a><span data-ttu-id="8d35c-102">COR_PRF_STATIC_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="8d35c-102">COR_PRF_STATIC_TYPE Enumeration</span></span>
<span data-ttu-id="8d35c-103">Indica si un campo es estático y, si lo es, la calidad estática que se aplica al campo.</span><span class="sxs-lookup"><span data-stu-id="8d35c-103">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="8d35c-104">Estos valores pueden combinarse mediante la operación OR bit a bit para indicar que el campo tiene varias cualidades estáticas.</span><span class="sxs-lookup"><span data-stu-id="8d35c-104">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8d35c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8d35c-105">Syntax</span></span>  
  
```  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="8d35c-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="8d35c-106">Members</span></span>  
  
|<span data-ttu-id="8d35c-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="8d35c-107">Member</span></span>|<span data-ttu-id="8d35c-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d35c-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="8d35c-109">El campo no es estático.</span><span class="sxs-lookup"><span data-stu-id="8d35c-109">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="8d35c-110">El campo es estático del dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="8d35c-110">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="8d35c-111">El campo es estático de subproceso.</span><span class="sxs-lookup"><span data-stu-id="8d35c-111">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="8d35c-112">El campo es estático de contexto.</span><span class="sxs-lookup"><span data-stu-id="8d35c-112">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="8d35c-113">El campo es la dirección virtual relativa (RVA)-estático.</span><span class="sxs-lookup"><span data-stu-id="8d35c-113">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8d35c-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d35c-114">Requirements</span></span>  
 <span data-ttu-id="8d35c-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d35c-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d35c-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="8d35c-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="8d35c-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8d35c-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8d35c-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d35c-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d35c-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8d35c-119">See Also</span></span>  
 [<span data-ttu-id="8d35c-120">Enumeraciones de generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="8d35c-120">Profiling Enumerations</span></span>](../../../../docs/framework/unmanaged-api/profiling/profiling-enumerations.md)
