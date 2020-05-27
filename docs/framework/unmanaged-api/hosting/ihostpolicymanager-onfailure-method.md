---
title: IHostPolicyManager::OnFailure (Método)
ms.date: 03/30/2017
api_name:
- IHostPolicyManager.OnFailure
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostPolicyManager::OnFailure
helpviewer_keywords:
- OnFailure method [.NET Framework hosting]
- IHostPolicyManager::OnFailure method [.NET Framework hosting]
ms.assetid: 77d3f31e-9a53-4349-9c02-610a71736d42
topic_type:
- apiref
ms.openlocfilehash: 8ad4943aa9bf1b66b34bcd83a5422a977b16518d
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804232"
---
# <a name="ihostpolicymanageronfailure-method"></a><span data-ttu-id="2b796-102">IHostPolicyManager::OnFailure (Método)</span><span class="sxs-lookup"><span data-stu-id="2b796-102">IHostPolicyManager::OnFailure Method</span></span>
<span data-ttu-id="2b796-103">Notifica al host que el Common Language Runtime (CLR) está a punto de realizar la acción especificada por una llamada al método [ICLRPolicyManager:: setactiononfailure (](iclrpolicymanager-setactiononfailure-method.md) en respuesta a un error de asignación de recursos o de recorte.</span><span class="sxs-lookup"><span data-stu-id="2b796-103">Notifies the host that the common language runtime (CLR) is about to take the action specified by a call to the [ICLRPolicyManager::SetActionOnFailure](iclrpolicymanager-setactiononfailure-method.md) method in response to a resource allocation or reclamation failure.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2b796-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2b796-104">Syntax</span></span>  
  
```cpp  
HRESULT OnFailure(  
    [in] EClrFailure   failure,  
    [in] EPolicyAction action  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2b796-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2b796-105">Parameters</span></span>  
 `failure`  
 <span data-ttu-id="2b796-106">de Uno de los valores de [eclrfailure (](eclrfailure-enumeration.md) , que indica el tipo de error al que responde el CLR.</span><span class="sxs-lookup"><span data-stu-id="2b796-106">[in] One of the [EClrFailure](eclrfailure-enumeration.md) values, indicating the kind of failure to which the CLR is responding.</span></span>  
  
 `action`  
 <span data-ttu-id="2b796-107">de Uno de los valores de [EPolicyAction](epolicyaction-enumeration.md) , que indica la acción que el CLR está tomando como respuesta `failure` .</span><span class="sxs-lookup"><span data-stu-id="2b796-107">[in] One of the [EPolicyAction](epolicyaction-enumeration.md) values, indicating the action the CLR is taking in response to `failure`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2b796-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2b796-108">Return Value</span></span>  
  
|<span data-ttu-id="2b796-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2b796-109">HRESULT</span></span>|<span data-ttu-id="2b796-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="2b796-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="2b796-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="2b796-111">S_OK</span></span>|<span data-ttu-id="2b796-112">`OnFailure`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2b796-112">`OnFailure` returned successfully.</span></span>|  
|<span data-ttu-id="2b796-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="2b796-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="2b796-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="2b796-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="2b796-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="2b796-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="2b796-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="2b796-116">The call timed out.</span></span>|  
|<span data-ttu-id="2b796-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="2b796-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="2b796-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="2b796-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="2b796-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="2b796-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="2b796-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="2b796-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="2b796-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="2b796-121">E_FAIL</span></span>|<span data-ttu-id="2b796-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="2b796-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="2b796-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="2b796-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="2b796-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="2b796-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2b796-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2b796-125">Requirements</span></span>  
 <span data-ttu-id="2b796-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2b796-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2b796-127">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="2b796-127">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2b796-128">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2b796-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2b796-129">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2b796-129">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2b796-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2b796-130">See also</span></span>

- [<span data-ttu-id="2b796-131">EClrFailure (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="2b796-131">EClrFailure Enumeration</span></span>](eclrfailure-enumeration.md)
- [<span data-ttu-id="2b796-132">EPolicyAction (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="2b796-132">EPolicyAction Enumeration</span></span>](epolicyaction-enumeration.md)
- [<span data-ttu-id="2b796-133">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2b796-133">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="2b796-134">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2b796-134">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
