---
title: ICLRProbingAssemblyEnum (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRProbingAssemblyEnum
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRProbingAssemblyEnum
helpviewer_keywords:
- ICLRProbingAssemblyEnum interface [.NET Framework hosting]
ms.assetid: e7d3ccab-b0f0-4872-8935-0ed72920171b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d471d7a33a048315b3a7fd9107baa0ad95a865c
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54678779"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="938b3-102">ICLRProbingAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="938b3-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="938b3-103">Proporciona métodos que permiten al host obtener las identidades de sondeo de un ensamblado mediante el uso de información de identidad del ensamblado que es interna de common language runtime (CLR), sin necesidad de crear o reconocer dicha identidad.</span><span class="sxs-lookup"><span data-stu-id="938b3-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="938b3-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="938b3-104">Methods</span></span>  
  
|<span data-ttu-id="938b3-105">Método</span><span class="sxs-lookup"><span data-stu-id="938b3-105">Method</span></span>|<span data-ttu-id="938b3-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="938b3-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="938b3-107">Get (método)</span><span class="sxs-lookup"><span data-stu-id="938b3-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="938b3-108">Obtiene la identidad del ensamblado en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="938b3-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="938b3-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="938b3-109">Remarks</span></span>  
 <span data-ttu-id="938b3-110">Los métodos como [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) devolver un `ICLRProbingAssemblyEnum` instancia.</span><span class="sxs-lookup"><span data-stu-id="938b3-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="938b3-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="938b3-111">Requirements</span></span>  
 <span data-ttu-id="938b3-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="938b3-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="938b3-113">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="938b3-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="938b3-114">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="938b3-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="938b3-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="938b3-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="938b3-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="938b3-116">See also</span></span>
- [<span data-ttu-id="938b3-117">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="938b3-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="938b3-118">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="938b3-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="938b3-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="938b3-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
