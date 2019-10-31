---
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
ms.openlocfilehash: 7b6a4be94e526e7b464b336d221eff936808635a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120572"
---
# <a name="iclrpolicymanagersetunhandledexceptionpolicy-method"></a><span data-ttu-id="5a118-102">ICLRPolicyManager::SetUnhandledExceptionPolicy (Método)</span><span class="sxs-lookup"><span data-stu-id="5a118-102">ICLRPolicyManager::SetUnhandledExceptionPolicy Method</span></span>
<span data-ttu-id="5a118-103">Especifica el comportamiento del Common Language Runtime (CLR) cuando se produce una excepción no controlada.</span><span class="sxs-lookup"><span data-stu-id="5a118-103">Specifies the behavior of the common language runtime (CLR) when an unhandled exception occurs.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5a118-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a118-104">Syntax</span></span>  
  
```cpp  
HRESULT SetUnhandledExceptionPolicy (  
    [in] EClrUnhandledExceptionPolicy policy  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5a118-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a118-105">Parameters</span></span>  
 `policy`  
 <span data-ttu-id="5a118-106">de Uno de los valores de [EClrUnhandledException (](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) , que indica si el CLR o el host establecen el comportamiento.</span><span class="sxs-lookup"><span data-stu-id="5a118-106">[in] One of the [EClrUnhandledException](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md) values, indicating whether the behavior is set by the CLR or the host.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5a118-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5a118-107">Return Value</span></span>  
  
|<span data-ttu-id="5a118-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5a118-108">HRESULT</span></span>|<span data-ttu-id="5a118-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="5a118-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="5a118-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="5a118-110">S_OK</span></span>|<span data-ttu-id="5a118-111">`SetUnhandledExceptionPolicy` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5a118-111">`SetUnhandledExceptionPolicy` returned successfully.</span></span>|  
|<span data-ttu-id="5a118-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="5a118-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="5a118-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="5a118-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="5a118-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="5a118-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="5a118-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="5a118-115">The call timed out.</span></span>|  
|<span data-ttu-id="5a118-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="5a118-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="5a118-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="5a118-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="5a118-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="5a118-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="5a118-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="5a118-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="5a118-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="5a118-120">E_FAIL</span></span>|<span data-ttu-id="5a118-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="5a118-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="5a118-122">Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="5a118-122">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="5a118-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="5a118-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5a118-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5a118-124">Remarks</span></span>  
 <span data-ttu-id="5a118-125">De forma predeterminada, el CLR es el controlador final de todas las excepciones no controladas y su comportamiento predeterminado es anular el proceso.</span><span class="sxs-lookup"><span data-stu-id="5a118-125">By default, the CLR is the final handler for all unhandled exceptions, and its default behavior is to tear down the process.</span></span> <span data-ttu-id="5a118-126">El host puede cambiar este comportamiento estableciendo el valor de `policy` en eHostDeterminedPolicy.</span><span class="sxs-lookup"><span data-stu-id="5a118-126">The host can change this behavior by setting the `policy` value to eHostDeterminedPolicy.</span></span> <span data-ttu-id="5a118-127">Este valor permite que el host implemente su propio comportamiento predeterminado, al igual que con las versiones anteriores de CLR.</span><span class="sxs-lookup"><span data-stu-id="5a118-127">This value allows the host to implement its own default behavior, as with earlier versions of the CLR.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5a118-128">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a118-128">Requirements</span></span>  
 <span data-ttu-id="5a118-129">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a118-129">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5a118-130">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="5a118-130">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5a118-131">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="5a118-131">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5a118-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5a118-132">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5a118-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a118-133">See also</span></span>

- [<span data-ttu-id="5a118-134">EClrUnhandledException (enumeración)</span><span class="sxs-lookup"><span data-stu-id="5a118-134">EClrUnhandledException Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eclrunhandledexception-enumeration.md)
- [<span data-ttu-id="5a118-135">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a118-135">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="5a118-136">ICLRPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a118-136">ICLRPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md)
- [<span data-ttu-id="5a118-137">IHostPolicyManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5a118-137">IHostPolicyManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostpolicymanager-interface.md)
