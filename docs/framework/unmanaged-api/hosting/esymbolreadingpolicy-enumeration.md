---
description: 'Más información sobre: enumeración ESymbolReadingPolicy ('
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
ms.openlocfilehash: e84c31343b589cb6019d88fafc9b94207c5f5892
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785424"
---
# <a name="esymbolreadingpolicy-enumeration"></a><span data-ttu-id="848fc-103">ESymbolReadingPolicy (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="848fc-103">ESymbolReadingPolicy Enumeration</span></span>

<span data-ttu-id="848fc-104">Contiene valores que establecen la Directiva para leer archivos de base de datos de programa (PDB).</span><span class="sxs-lookup"><span data-stu-id="848fc-104">Contains values that set the policy for reading program database (PDB) files.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="848fc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="848fc-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    eSymbolReadingNever,  
    eSymbolReadingAlways,  
    eSymbolReadingFullTrustOnly  
} ESymbolReadingPolicy;  
```  
  
## <a name="members"></a><span data-ttu-id="848fc-106">Members</span><span class="sxs-lookup"><span data-stu-id="848fc-106">Members</span></span>  
  
|<span data-ttu-id="848fc-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="848fc-107">Member</span></span>|<span data-ttu-id="848fc-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="848fc-108">Description</span></span>|  
|------------|-----------------|  
|`eSymbolReadingAlways`|<span data-ttu-id="848fc-109">Especifica que el depurador siempre debe leer los archivos PDB.</span><span class="sxs-lookup"><span data-stu-id="848fc-109">Specifies that the debugger should always read PDB files.</span></span>|  
|`eSymbolReadingFullTrustOnly`|<span data-ttu-id="848fc-110">Especifica que el depurador debe leer solo los archivos PDB asociados a los ensamblados de plena confianza.</span><span class="sxs-lookup"><span data-stu-id="848fc-110">Specifies that the debugger should read only PDB files that are associated with full-trust assemblies.</span></span>|  
|`eSymbolReadingNever`|<span data-ttu-id="848fc-111">Especifica que el depurador nunca debe leer archivos PDB.</span><span class="sxs-lookup"><span data-stu-id="848fc-111">Specifies that the debugger should never read PDB files.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="848fc-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="848fc-112">Remarks</span></span>  

 <span data-ttu-id="848fc-113">La `ESymbolReadingPolicy` enumeración se usa con el método [ICLRDebugManager:: SetSymbolReadingPolicy (](iclrdebugmanager-setsymbolreadingpolicy-method.md) .</span><span class="sxs-lookup"><span data-stu-id="848fc-113">The `ESymbolReadingPolicy` enumeration is used with the [ICLRDebugManager::SetSymbolReadingPolicy](iclrdebugmanager-setsymbolreadingpolicy-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="848fc-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="848fc-114">Requirements</span></span>  

 <span data-ttu-id="848fc-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="848fc-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="848fc-116">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="848fc-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="848fc-117">**Biblioteca:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="848fc-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="848fc-118">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="848fc-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="848fc-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="848fc-119">See also</span></span>

- [<span data-ttu-id="848fc-120">Enumeraciones para hosts</span><span class="sxs-lookup"><span data-stu-id="848fc-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
