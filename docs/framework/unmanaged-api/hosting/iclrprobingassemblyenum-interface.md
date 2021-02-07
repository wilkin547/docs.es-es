---
description: 'Más información acerca de: ICLRProbingAssemblyEnum (interfaz)'
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
ms.openlocfilehash: 1fd11e237f02bab85ec2b41df49d7d8a2f27e1e1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716518"
---
# <a name="iclrprobingassemblyenum-interface"></a><span data-ttu-id="4c106-103">ICLRProbingAssemblyEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4c106-103">ICLRProbingAssemblyEnum Interface</span></span>

<span data-ttu-id="4c106-104">Proporciona métodos que permiten al host obtener las identidades de sondeo de un ensamblado mediante la información de identidad del ensamblado que es interna del Common Language Runtime (CLR), sin necesidad de crear o comprender esa identidad.</span><span class="sxs-lookup"><span data-stu-id="4c106-104">Provides methods that enable the host to get the probing identities of an assembly by using the assembly's identity information that is internal to the common language runtime (CLR), without needing to create or understand that identity.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4c106-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4c106-105">Methods</span></span>  
  
|<span data-ttu-id="4c106-106">Método</span><span class="sxs-lookup"><span data-stu-id="4c106-106">Method</span></span>|<span data-ttu-id="4c106-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4c106-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="4c106-108">Get (método)</span><span class="sxs-lookup"><span data-stu-id="4c106-108">Get Method</span></span>](iclrprobingassemblyenum-get-method.md)|<span data-ttu-id="4c106-109">Obtiene la identidad del ensamblado en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="4c106-109">Gets the assembly identity at the specified index.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4c106-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4c106-110">Remarks</span></span>  

 <span data-ttu-id="4c106-111">Los métodos como [ICLRAssemblyIdentityManager:: getprobingassembliesfromreference (](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) devuelven una `ICLRProbingAssemblyEnum` instancia de.</span><span class="sxs-lookup"><span data-stu-id="4c106-111">Methods such as [ICLRAssemblyIdentityManager::GetProbingAssembliesFromReference](iclrassemblyidentitymanager-getprobingassembliesfromreference-method.md) return an `ICLRProbingAssemblyEnum` instance.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4c106-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4c106-112">Requirements</span></span>  

 <span data-ttu-id="4c106-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4c106-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4c106-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4c106-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4c106-115">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4c106-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4c106-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4c106-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4c106-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4c106-117">See also</span></span>

- [<span data-ttu-id="4c106-118">ICLRAssemblyIdentityManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4c106-118">ICLRAssemblyIdentityManager Interface</span></span>](iclrassemblyidentitymanager-interface.md)
- [<span data-ttu-id="4c106-119">ICLRAssemblyReferenceList (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4c106-119">ICLRAssemblyReferenceList Interface</span></span>](iclrassemblyreferencelist-interface.md)
- [<span data-ttu-id="4c106-120">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="4c106-120">Hosting Interfaces</span></span>](hosting-interfaces.md)
