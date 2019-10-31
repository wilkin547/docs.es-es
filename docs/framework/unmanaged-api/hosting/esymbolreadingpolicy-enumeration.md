---
title: ESymbolReadingPolicy (Enumeración)
ms.date: 03/30/2017
api_name:
- ESymbolReadingPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ESymbolReadingPolicy
helpviewer_keywords:
- ESymbolReadingPolicy enumeration [.NET Framework hosting]
ms.assetid: 4dc6c80d-b694-480b-a378-d5b18420ce17
topic_type:
- apiref
ms.openlocfilehash: 786ff6895383fc18dcfedb26fab344f80f04c1df
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138207"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="cc8db-102">ESymbolReadingPolicy (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="cc8db-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="cc8db-103">Contiene valores que establecen la Directiva para leer archivos de base de datos de programa (PDB).</span><span class="sxs-lookup"><span data-stu-id="cc8db-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc8db-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc8db-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="cc8db-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="cc8db-105">Members</span></span>  
  
|<span data-ttu-id="cc8db-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="cc8db-106">Member</span></span>|<span data-ttu-id="cc8db-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="cc8db-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="cc8db-108">Especifica que el depurador siempre debe leer los archivos PDB.</span><span class="sxs-lookup"><span data-stu-id="cc8db-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="cc8db-109">Especifica que el depurador debe leer solo los archivos PDB asociados a los ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="cc8db-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="cc8db-110">Especifica que el depurador nunca debe leer archivos PDB.</span><span class="sxs-lookup"><span data-stu-id="cc8db-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="cc8db-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="cc8db-111">Remarks</span></span>  
 <span data-ttu-id="cc8db-112">La enumeración `ESymbolReadingPolicy` se usa con el método [ICLRDebugManager:: SetSymbolReadingPolicy (](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) .</span><span class="sxs-lookup"><span data-stu-id="cc8db-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc8db-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc8db-113">Requirements</span></span>  
 <span data-ttu-id="cc8db-114">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc8db-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc8db-115">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="cc8db-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="cc8db-116">**Biblioteca:** MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="cc8db-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="cc8db-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc8db-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc8db-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc8db-118">See also</span></span>

- [<span data-ttu-id="cc8db-119">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="cc8db-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
