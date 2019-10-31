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
ms.openlocfilehash: e1459c1604f3f8f043fd9b61533235ab7861c910
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120561"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="f3065-102">ICLRProbingAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3065-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="f3065-103">Proporciona métodos que permiten al host obtener las identidades de sondeo de un ensamblado mediante la información de identidad del ensamblado que es interna del Common Language Runtime (CLR), sin necesidad de crear o comprender esa identidad.</span><span class="sxs-lookup"><span data-stu-id="f3065-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f3065-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f3065-104">Methods</span></span>  
  
|<span data-ttu-id="f3065-105">Método</span><span class="sxs-lookup"><span data-stu-id="f3065-105">Method</span></span>|<span data-ttu-id="f3065-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3065-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f3065-107">Get (método)</span><span class="sxs-lookup"><span data-stu-id="f3065-107">Get Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="f3065-108">Obtiene la identidad del ensamblado en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="f3065-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f3065-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f3065-109">Remarks</span></span>  
 <span data-ttu-id="f3065-110">Los métodos como [ICLRAssemblyIdentityManager:: getprobingassembliesfromreference (](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) devuelven una instancia de `ICLRProbingAssemblyEnum`.</span><span class="sxs-lookup"><span data-stu-id="f3065-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f3065-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3065-111">Requirements</span></span>  
 <span data-ttu-id="f3065-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3065-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3065-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="f3065-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="f3065-114">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f3065-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f3065-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f3065-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3065-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f3065-116">See also</span></span>

- [<span data-ttu-id="f3065-117">ICLRAssemblyIdentityManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3065-117">ICLRAssemblyIdentityManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="f3065-118">ICLRAssemblyReferenceList (interfaz)</span><span class="sxs-lookup"><span data-stu-id="f3065-118">ICLRAssemblyReferenceList Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="f3065-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="f3065-119">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
