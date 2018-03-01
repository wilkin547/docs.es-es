---
title: "ESymbolReadingPolicy (Enumeración)"
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
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4fdb18a343f91e85619f6d62e466fdd558044727
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="61a76-102">ESymbolReadingPolicy (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="61a76-102">ESymbolReadingPolicy Enumeration</span></span>
<span data-ttu-id="61a76-103">Contiene valores que establecen la directiva para leer los archivos de programa (PDB) de la base de datos.</span><span class="sxs-lookup"><span data-stu-id="61a76-103">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="61a76-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="61a76-104">Syntax</span></span>  
  
```  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="61a76-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="61a76-105">Members</span></span>  
  
|<span data-ttu-id="61a76-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="61a76-106">Member</span></span>|<span data-ttu-id="61a76-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="61a76-107">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="61a76-108">Especifica que el depurador siempre debe leer los archivos PDB.</span><span class="sxs-lookup"><span data-stu-id="61a76-108">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="61a76-109">Especifica que el depurador debe leer solo PDB (archivos) que están asociados a ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="61a76-109">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="61a76-110">Especifica que el depurador nunca debe leer los archivos PDB.</span><span class="sxs-lookup"><span data-stu-id="61a76-110">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="61a76-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="61a76-111">Remarks</span></span>  
 <span data-ttu-id="61a76-112">El `ESymbolReadingPolicy` enumeración se utiliza con la [ICLRDebugManager:: SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="61a76-112">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="61a76-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="61a76-113">Requirements</span></span>  
 <span data-ttu-id="61a76-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="61a76-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="61a76-115">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="61a76-115">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="61a76-116">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="61a76-116">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="61a76-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="61a76-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="61a76-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="61a76-118">See Also</span></span>  
 [<span data-ttu-id="61a76-119">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="61a76-119">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
