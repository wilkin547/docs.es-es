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
ms.openlocfilehash: e1e114070f39e75254fc1bc0f8c1bf3e4733d5a2
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703375"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="3efae-102">ICLRProbingAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3efae-102">ICLRProbingAssemblyEnum Interface</span></span>
<span data-ttu-id="3efae-103">Proporciona métodos que permiten al host obtener las identidades de sondeo de un ensamblado mediante la información de identidad del ensamblado que es interna del Common Language Runtime (CLR), sin necesidad de crear o comprender esa identidad.</span><span class="sxs-lookup"><span data-stu-id="3efae-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3efae-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="3efae-104">Methods</span></span>  
  
|<span data-ttu-id="3efae-105">Método</span><span class="sxs-lookup"><span data-stu-id="3efae-105">Method</span></span>|<span data-ttu-id="3efae-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="3efae-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3efae-107">Get (Método)</span><span class="sxs-lookup"><span data-stu-id="3efae-107">Get Method</span></span>](iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="3efae-108">Obtiene la identidad del ensamblado en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="3efae-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3efae-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3efae-109">Remarks</span></span>  
 <span data-ttu-id="3efae-110">Los métodos como [ICLRAssemblyIdentityManager:: getprobingassembliesfromreference (](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) devuelven una `ICLRProbingAssemblyEnum` instancia de.</span><span class="sxs-lookup"><span data-stu-id="3efae-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3efae-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3efae-111">Requirements</span></span>  
 <span data-ttu-id="3efae-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3efae-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3efae-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3efae-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3efae-114">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="3efae-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3efae-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3efae-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3efae-116">Consulta también</span><span class="sxs-lookup"><span data-stu-id="3efae-116">See also</span></span>

- [<span data-ttu-id="3efae-117">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3efae-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="3efae-118">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3efae-118">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="3efae-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="3efae-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
