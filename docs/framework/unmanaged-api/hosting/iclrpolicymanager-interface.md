---
title: ICLRPolicyManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager
helpviewer_keywords:
- ICLRPolicyManager interface [.NET Framework hosting]
ms.assetid: 5c834aa1-f2db-408a-b230-c7bec093d364
topic_type:
- apiref
ms.openlocfilehash: 631301a10aee96bb00aeda6b0b8695f0aea186a8
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703482"
---
# <a name="iclrpolicymanager-interface"></a><span data-ttu-id="06636-102">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="06636-102">ICLRPolicyManager Interface</span></span>
<span data-ttu-id="06636-103">Proporciona métodos que permiten al host especificar las acciones de directiva que deben realizarse en caso de que se produzcan errores y tiempos de espera.</span><span class="sxs-lookup"><span data-stu-id="06636-103">Provides methods that allow the host to specify policy actions to be taken in the event of failures and timeouts.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="06636-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="06636-104">Methods</span></span>  
  
|<span data-ttu-id="06636-105">Método</span><span class="sxs-lookup"><span data-stu-id="06636-105">Method</span></span>|<span data-ttu-id="06636-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="06636-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="06636-107">Método SetActionOnFailure</span><span class="sxs-lookup"><span data-stu-id="06636-107">SetActionOnFailure Method</span></span>](iclrpolicymanager-setactiononfailure-method.md)|<span data-ttu-id="06636-108">Especifica la acción de la Directiva que debe realizar el Common Language Runtime (CLR) cuando se produce el error especificado.</span><span class="sxs-lookup"><span data-stu-id="06636-108">Specifies the policy action the common language runtime (CLR) should take when the specified failure occurs.</span></span>|  
|[<span data-ttu-id="06636-109">Método SetActionOnTimeout</span><span class="sxs-lookup"><span data-stu-id="06636-109">SetActionOnTimeout Method</span></span>](iclrpolicymanager-setactionontimeout-method.md)|<span data-ttu-id="06636-110">Especifica la acción de la Directiva que el CLR debe realizar cuando se agota el tiempo de espera de la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="06636-110">Specifies the policy action the CLR should take when the specified operation times out.</span></span>|  
|[<span data-ttu-id="06636-111">Método SetDefaultAction</span><span class="sxs-lookup"><span data-stu-id="06636-111">SetDefaultAction Method</span></span>](iclrpolicymanager-setdefaultaction-method.md)|<span data-ttu-id="06636-112">Especifica la acción de la Directiva que el CLR debe realizar cuando se produce la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="06636-112">Specifies the policy action the CLR should take when the specified operation occurs.</span></span>|  
|[<span data-ttu-id="06636-113">Método SetTimeout</span><span class="sxs-lookup"><span data-stu-id="06636-113">SetTimeout Method</span></span>](iclrpolicymanager-settimeout-method.md)|<span data-ttu-id="06636-114">Establece un valor de tiempo de espera para la operación especificada.</span><span class="sxs-lookup"><span data-stu-id="06636-114">Sets a timeout value for the specified operation.</span></span>|  
|[<span data-ttu-id="06636-115">Método SetTimeoutAndAction</span><span class="sxs-lookup"><span data-stu-id="06636-115">SetTimeoutAndAction Method</span></span>](iclrpolicymanager-settimeoutandaction-method.md)|<span data-ttu-id="06636-116">Establece un valor de tiempo de espera para la operación especificada y especifica la acción de la Directiva que el CLR debe realizar cuando se produce la operación.</span><span class="sxs-lookup"><span data-stu-id="06636-116">Sets a timeout value for the specified operation, and specifies the policy action the CLR should take when the operation occurs.</span></span>|  
|[<span data-ttu-id="06636-117">Método SetUnhandledExceptionPolicy</span><span class="sxs-lookup"><span data-stu-id="06636-117">SetUnhandledExceptionPolicy Method</span></span>](iclrpolicymanager-setunhandledexceptionpolicy-method.md)|<span data-ttu-id="06636-118">Especifica el comportamiento de CLR cuando se produce una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="06636-118">Specifies the behavior of the CLR when an unhandled exception occurs.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="06636-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="06636-119">Requirements</span></span>  
 <span data-ttu-id="06636-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06636-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06636-121">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="06636-121">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="06636-122">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="06636-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="06636-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06636-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06636-124">Consulta también</span><span class="sxs-lookup"><span data-stu-id="06636-124">See also</span></span>

- [<span data-ttu-id="06636-125">EClrFailure (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="06636-125">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="06636-126">EClrOperation (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="06636-126">EClrOperation Enumeration</span></span>](eclroperation-enumeration.md)
- [<span data-ttu-id="06636-127">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="06636-127">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="06636-128">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="06636-128">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
