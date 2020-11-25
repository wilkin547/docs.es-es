---
title: ICLRHostBindingPolicyManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRHostBindingPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostBindingPolicyManager
helpviewer_keywords:
- ICLRHostBindingPolicyManager interface [.NET Framework hosting]
ms.assetid: f9da168b-366b-4b2b-bdb9-330b6bad5a6b
topic_type:
- apiref
ms.openlocfilehash: 49d1ee4dd0965d4ae5b54b53208809cfbdf7e718
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95725640"
---
# <a name="iclrhostbindingpolicymanager-interface"></a><span data-ttu-id="608aa-102">ICLRHostBindingPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="608aa-102">ICLRHostBindingPolicyManager Interface</span></span>

<span data-ttu-id="608aa-103">Proporciona métodos para que el host evalúe la Directiva de enlace actual y comunique los cambios de la Directiva para un ensamblado especificado.</span><span class="sxs-lookup"><span data-stu-id="608aa-103">Provides methods for the host to evaluate current binding policy and communicate policy changes for a specified assembly.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="608aa-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="608aa-104">Methods</span></span>  
  
|<span data-ttu-id="608aa-105">Método</span><span class="sxs-lookup"><span data-stu-id="608aa-105">Method</span></span>|<span data-ttu-id="608aa-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="608aa-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="608aa-107">Método EvaluatePolicy</span><span class="sxs-lookup"><span data-stu-id="608aa-107">EvaluatePolicy Method</span></span>](iclrhostbindingpolicymanager-evaluatepolicy-method.md)|<span data-ttu-id="608aa-108">Evalúa la Directiva de enlace en nombre del host.</span><span class="sxs-lookup"><span data-stu-id="608aa-108">Evaluates binding policy on behalf of the host.</span></span>|  
|[<span data-ttu-id="608aa-109">Método ModifyApplicationPolicy</span><span class="sxs-lookup"><span data-stu-id="608aa-109">ModifyApplicationPolicy Method</span></span>](iclrhostbindingpolicymanager-modifyapplicationpolicy-method.md)|<span data-ttu-id="608aa-110">Modifica la Directiva de enlace para el ensamblado especificado y crea una nueva versión de la Directiva.</span><span class="sxs-lookup"><span data-stu-id="608aa-110">Modifies the binding policy for the specified assembly, and creates a new version of the policy.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="608aa-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="608aa-111">Requirements</span></span>  

 <span data-ttu-id="608aa-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="608aa-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="608aa-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="608aa-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="608aa-114">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="608aa-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="608aa-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="608aa-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="608aa-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="608aa-116">See also</span></span>

- [<span data-ttu-id="608aa-117">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="608aa-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="608aa-118">IHostAssemblyStore (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="608aa-118">IHostAssemblyStore Interface</span></span>](ihostassemblystore-interface.md)
- [<span data-ttu-id="608aa-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="608aa-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
