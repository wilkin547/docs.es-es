---
description: 'Más información sobre: ICLRPolicyManager:: SetUnhandledExceptionPolicy ((método)'
title: ICLRPolicyManager::SetUnhandledExceptionPolicy (Método)
ms.date: 03/30/2017
api_name:
- ICLRPolicyManager.SetUnhandledExceptionPolicy
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy
helpviewer_keywords:
- ICLRPolicyManager::SetUnhandledExceptionPolicy method [.NET Framework hosting]
- SetUnhandledExceptionPolicy method [.NET Framework hosting]
ms.assetid: 5268480e-280a-4931-b7a3-dc3ffdf7f78f
topic_type:
- apiref
ms.openlocfilehash: 489127bb00b2b65466460baa3cfd31439672cd1c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716554"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="3bb1e-103">ICLRPolicyManager::SetUnhandledExceptionPolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="3bb1e-103">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>

<span data-ttu-id="3bb1e-104">Especifica el comportamiento del Common Language Runtime (CLR) cuando se produce una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="3bb1e-104">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3bb1e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3bb1e-105">Syntax</span></span>  
  
```cpp  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3bb1e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3bb1e-106">Parameters</span></span>  

 `policy`  
 <span data-ttu-id="3bb1e-107">de Uno de los valores de [EClrUnhandledException (](eclrunhandledexception-enumeration.md) , que indica si el CLR o el host establecen el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="3bb1e-107">[in] One of the [EClrUnhandledException](eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3bb1e-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3bb1e-108">Return Value</span></span>  
  
|<span data-ttu-id="3bb1e-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3bb1e-109">HRESULT</span></span>|<span data-ttu-id="3bb1e-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="3bb1e-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3bb1e-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="3bb1e-111">S_OK</span></span>|<span data-ttu-id="3bb1e-112">`SetUnhandledExceptionPolicy` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3bb1e-112">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="3bb1e-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="3bb1e-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="3bb1e-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="3bb1e-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="3bb1e-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="3bb1e-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="3bb1e-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="3bb1e-116">The call timed out.</span></span>|  
|<span data-ttu-id="3bb1e-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="3bb1e-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="3bb1e-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="3bb1e-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="3bb1e-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="3bb1e-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="3bb1e-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="3bb1e-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="3bb1e-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="3bb1e-121">E_FAIL</span></span>|<span data-ttu-id="3bb1e-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="3bb1e-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="3bb1e-123">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="3bb1e-123">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="3bb1e-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="3bb1e-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3bb1e-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="3bb1e-125">Remarks</span></span>  

 <span data-ttu-id="3bb1e-126">De forma predeterminada, el CLR es el controlador final de todas las excepciones no controladas y su comportamiento predeterminado es anular el proceso.</span><span class="sxs-lookup"><span data-stu-id="3bb1e-126">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="3bb1e-127">El host puede cambiar este comportamiento estableciendo el `policy` valor en eHostDeterminedPolicy.</span><span class="sxs-lookup"><span data-stu-id="3bb1e-127">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="3bb1e-128">Este valor permite que el host implemente su propio comportamiento predeterminado, al igual que con las versiones anteriores de CLR.</span><span class="sxs-lookup"><span data-stu-id="3bb1e-128">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3bb1e-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3bb1e-129">Requirements</span></span>  

 <span data-ttu-id="3bb1e-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3bb1e-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3bb1e-131">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="3bb1e-131">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="3bb1e-132">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3bb1e-132">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3bb1e-133">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3bb1e-133">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3bb1e-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="3bb1e-134">See also</span></span>

- [<span data-ttu-id="3bb1e-135">EClrUnhandledException (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="3bb1e-135">EClrUnhandledException Enumeration</span></span>](eclrunhandledexception-enumeration.md)
- [<span data-ttu-id="3bb1e-136">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3bb1e-136">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="3bb1e-137">ICLRPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3bb1e-137">ICLRPolicyManager Interface</span></span>](iclrpolicymanager-interface.md)
- [<span data-ttu-id="3bb1e-138">IHostPolicyManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3bb1e-138">IHostPolicyManager Interface</span></span>](ihostpolicymanager-interface.md)
