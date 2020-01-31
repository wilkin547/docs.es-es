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
ms.openlocfilehash: 880c9bd186d6cb2acb277e9cc55d3063fb8d51d8
ms.sourcegitcommit: b11efd71c3d5ce3d9449c8d4345481b9f21392c6
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/29/2020
ms.locfileid: "76867045"
---
# <a name="cor_prf_static_type-enumeration"></a><span data-ttu-id="81aa0-102">COR_PRF_STATIC_TYPE (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="81aa0-102">COR_PRF_STATIC_TYPE Enumeration</span></span>
<span data-ttu-id="81aa0-103">Indica si un campo es estático y, si lo es, la calidad estática que se aplica al campo.</span><span class="sxs-lookup"><span data-stu-id="81aa0-103">Indicates whether a field is static and, if so, the static quality that applies to the field.</span></span> <span data-ttu-id="81aa0-104">Estos valores se pueden combinar mediante la operación OR bit a bit para indicar que el campo tiene varias cualidades estáticas diferentes.</span><span class="sxs-lookup"><span data-stu-id="81aa0-104">These values can be combined using the bitwise OR operation to indicate that the field has multiple, different static qualities.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="81aa0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81aa0-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    COR_PRF_FIELD_NOT_A_STATIC = 0x0,  
    COR_PRF_FIELD_APP_DOMAIN_STATIC = 0x1,  
    COR_PRF_FIELD_THREAD_STATIC = 0x2,  
    COR_PRF_FIELD_CONTEXT_STATIC = 0x4,  
    COR_PRF_FIELD_RVA_STATIC = 0x8  
} COR_PRF_STATIC_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="81aa0-106">Miembros</span><span class="sxs-lookup"><span data-stu-id="81aa0-106">Members</span></span>  
  
|<span data-ttu-id="81aa0-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="81aa0-107">Member</span></span>|<span data-ttu-id="81aa0-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="81aa0-108">Description</span></span>|  
|------------|-----------------|  
|`COR_PRF_FIELD_NOT_A_STATIC`|<span data-ttu-id="81aa0-109">El campo no es estático.</span><span class="sxs-lookup"><span data-stu-id="81aa0-109">The field is not static.</span></span>|  
|`COR_PRF_FIELD_APP_DOMAIN_STATIC`|<span data-ttu-id="81aa0-110">El campo es dominio de aplicación-estático.</span><span class="sxs-lookup"><span data-stu-id="81aa0-110">The field is application domain-static.</span></span>|  
|`COR_PRF_FIELD_THREAD_STATIC`|<span data-ttu-id="81aa0-111">El campo es estático de subproceso.</span><span class="sxs-lookup"><span data-stu-id="81aa0-111">The field is thread-static.</span></span>|  
|`COR_PRF_FIELD_CONTEXT_STATIC`|<span data-ttu-id="81aa0-112">El campo es de contexto estático.</span><span class="sxs-lookup"><span data-stu-id="81aa0-112">The field is context-static.</span></span>|  
|`COR_PRF_FIELD_RVA_STATIC`|<span data-ttu-id="81aa0-113">El campo es la dirección virtual relativa (RVA)-static.</span><span class="sxs-lookup"><span data-stu-id="81aa0-113">The field is relative virtual address (RVA)-static.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81aa0-114">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="81aa0-114">Requirements</span></span>  
 <span data-ttu-id="81aa0-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81aa0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81aa0-116">**Encabezado:** CorProf.idl, CorProf.h</span><span class="sxs-lookup"><span data-stu-id="81aa0-116">**Header:** CorProf.idl, CorProf.h</span></span>  
  
 <span data-ttu-id="81aa0-117">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="81aa0-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="81aa0-118">**.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81aa0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81aa0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="81aa0-119">See also</span></span>

- [<span data-ttu-id="81aa0-120">Enumeraciones para generación de perfiles</span><span class="sxs-lookup"><span data-stu-id="81aa0-120">Profiling Enumerations</span></span>](profiling-enumerations.md)
