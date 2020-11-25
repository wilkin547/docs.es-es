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
ms.openlocfilehash: 6df08889af30542af5a128cbffc38a57ce640fde
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728932"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="8d52c-102">ICLRProbingAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d52c-102">ICLRProbingAssemblyEnum Interface</span></span>

<span data-ttu-id="8d52c-103">Proporciona métodos que permiten al host obtener las identidades de sondeo de un ensamblado mediante la información de identidad del ensamblado que es interna del Common Language Runtime (CLR), sin necesidad de crear o comprender esa identidad.</span><span class="sxs-lookup"><span data-stu-id="8d52c-103">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8d52c-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="8d52c-104">Methods</span></span>  
  
|<span data-ttu-id="8d52c-105">Método</span><span class="sxs-lookup"><span data-stu-id="8d52c-105">Method</span></span>|<span data-ttu-id="8d52c-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="8d52c-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8d52c-107">Get (método)</span><span class="sxs-lookup"><span data-stu-id="8d52c-107">Get Method</span></span>](iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="8d52c-108">Obtiene la identidad del ensamblado en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="8d52c-108">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8d52c-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8d52c-109">Remarks</span></span>  

 <span data-ttu-id="8d52c-110">Los métodos como [ICLRAssemblyIdentityManager:: getprobingassembliesfromreference (](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) devuelven una `ICLRProbingAssemblyEnum` instancia de.</span><span class="sxs-lookup"><span data-stu-id="8d52c-110">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8d52c-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8d52c-111">Requirements</span></span>  

 <span data-ttu-id="8d52c-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8d52c-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8d52c-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="8d52c-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8d52c-114">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8d52c-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8d52c-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8d52c-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8d52c-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8d52c-116">See also</span></span>

- [<span data-ttu-id="8d52c-117">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d52c-117">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="8d52c-118">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8d52c-118">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="8d52c-119">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="8d52c-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
