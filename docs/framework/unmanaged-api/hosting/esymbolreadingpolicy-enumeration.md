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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 45b6b8593331801dd237d0a730afbd5a6a714bbf
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67774181"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="27014-102">ESymbolReadingPolicy (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="27014-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="27014-103">Contiene valores que establecen la directiva para leer los archivos de programa (PDB) de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="27014-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27014-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27014-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="27014-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="27014-105">Members</span></span>  
  
|<span data-ttu-id="27014-106">Member</span><span class="sxs-lookup"><span data-stu-id="27014-106">Member</span></span>|<span data-ttu-id="27014-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="27014-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="27014-108">Especifica que el depurador siempre debe leer los archivos PDB.</span><span class="sxs-lookup"><span data-stu-id="27014-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="27014-109">Especifica que el depurador debe leer sólo los archivos PDB asociados a ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="27014-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="27014-110">Especifica que el depurador nunca debe leer los archivos PDB.</span><span class="sxs-lookup"><span data-stu-id="27014-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="27014-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="27014-111">Remarks</span></span>  
 <span data-ttu-id="27014-112">El `ESymbolReadingPolicy` enumeración se utiliza con el [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="27014-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="27014-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27014-113">Requirements</span></span>  
 <span data-ttu-id="27014-114">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27014-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27014-115">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="27014-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="27014-116">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="27014-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="27014-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27014-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27014-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="27014-118">See also</span></span>

- [<span data-ttu-id="27014-119">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="27014-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
