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
ms.openlocfilehash: 118345f246de3d7ee68d51cf37e8cdea9de1fdba
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59094299"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="5b532-102">ICLRProbingAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5b532-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="5b532-103">Proporciona métodos que permiten al host obtener las identidades de sondeo de un ensamblado mediante el uso de información de identidad del ensamblado que es interna de common language runtime (CLR), sin necesidad de crear o reconocer dicha identidad.</span><span class="sxs-lookup"><span data-stu-id="5b532-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5b532-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5b532-104">Methods</span></span>  
  
|<span data-ttu-id="5b532-105">Método</span><span class="sxs-lookup"><span data-stu-id="5b532-105">Method</span></span>|<span data-ttu-id="5b532-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5b532-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5b532-107">Get (método)</span><span class="sxs-lookup"><span data-stu-id="5b532-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="5b532-108">Obtiene la identidad del ensamblado en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="5b532-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5b532-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5b532-109">Remarks</span></span>  
 <span data-ttu-id="5b532-110">Los métodos como [ICLRAssemblyIdentityManager](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) devolver un `ICLRProbingAssemblyEnum` instancia.</span><span class="sxs-lookup"><span data-stu-id="5b532-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b532-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5b532-111">Requirements</span></span>  
 <span data-ttu-id="5b532-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5b532-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b532-113">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5b532-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5b532-114">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5b532-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5b532-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b532-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b532-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5b532-116">See also</span></span>

- [<span data-ttu-id="5b532-117">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5b532-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="5b532-118">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5b532-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="5b532-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="5b532-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
