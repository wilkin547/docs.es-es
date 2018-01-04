---
title: ICLRProbingAssemblyEnum (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRProbingAssemblyEnum
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRProbingAssemblyEnum
helpviewer_keywords: ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 31f3bfcb2b70bda952f0e4bb43dd8b0067e6ef1a
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="ef9ea-102">ICLRProbingAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef9ea-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="ef9ea-103">Proporciona métodos que permiten al host obtener las identidades de sondeo de un ensamblado mediante el uso de información de identidad del ensamblado que es interno de common language runtime (CLR), sin necesidad de crear o reconocer dicha identidad.</span><span class="sxs-lookup"><span data-stu-id="ef9ea-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="ef9ea-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="ef9ea-104">Methods</span></span>  
  
|<span data-ttu-id="ef9ea-105">Método</span><span class="sxs-lookup"><span data-stu-id="ef9ea-105">Method</span></span>|<span data-ttu-id="ef9ea-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="ef9ea-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="ef9ea-107">Get (método)</span><span class="sxs-lookup"><span data-stu-id="ef9ea-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="ef9ea-108">Obtiene la identidad del ensamblado en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="ef9ea-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ef9ea-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ef9ea-109">Remarks</span></span>  
 <span data-ttu-id="ef9ea-110">Métodos como [ICLRAssemblyIdentityManager:: GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) devolver un `ICLRProbingAssemblyEnum` instancia.</span><span class="sxs-lookup"><span data-stu-id="ef9ea-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ef9ea-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ef9ea-111">Requirements</span></span>  
 <span data-ttu-id="ef9ea-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ef9ea-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ef9ea-113">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="ef9ea-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ef9ea-114">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ef9ea-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ef9ea-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ef9ea-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ef9ea-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="ef9ea-116">See Also</span></span>  
 [<span data-ttu-id="ef9ea-117">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef9ea-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)  
 [<span data-ttu-id="ef9ea-118">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ef9ea-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)  
 [<span data-ttu-id="ef9ea-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="ef9ea-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
