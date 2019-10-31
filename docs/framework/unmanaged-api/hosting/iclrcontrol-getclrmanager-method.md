---
title: ICLRControl::GetCLRManager (Método)
ms.date: 03/30/2017
api_name:
- ICLRControl.GetCLRManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRControl::GetCLRManager
helpviewer_keywords:
- GetCLRManager method [.NET Framework hosting]
- ICLRControl::GetCLRManager method [.NET Framework hosting]
ms.assetid: 8a11bfa4-cbb0-4082-82b5-f9fba66c93f5
topic_type:
- apiref
ms.openlocfilehash: fa9608423456caeb6020e883a14f2c41583ac4d9
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126611"
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="37d4c-102">ICLRControl::GetCLRManager (Método)</span><span class="sxs-lookup"><span data-stu-id="37d4c-102">ICLRControl::GetCLRManager Method</span></span>
<span data-ttu-id="37d4c-103">Obtiene un puntero de interfaz a una instancia de cualquiera de los tipos de administrador que el host puede usar para configurar el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="37d4c-103">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37d4c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37d4c-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="37d4c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="37d4c-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="37d4c-106">de `IID` del tipo de administrador que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="37d4c-106">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="37d4c-107">Se admiten los siguientes valores de `IID`.</span><span class="sxs-lookup"><span data-stu-id="37d4c-107">The following `IID` values are supported.</span></span>  
  
- <span data-ttu-id="37d4c-108">IID_ICLRDebugManager: especifica que `ppObject` será de tipo [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="37d4c-108">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](../../../../docs/framework/unmanaged-api/hosting/iclrdebugmanager-interface.md).</span></span>  
  
- <span data-ttu-id="37d4c-109">IID_ICLRErrorReportingManager: especifica que `ppObject` será de tipo [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="37d4c-109">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md).</span></span>  
  
- <span data-ttu-id="37d4c-110">IID_ICLRGCManager: especifica que `ppObject` será de tipo [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="37d4c-110">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](../../../../docs/framework/unmanaged-api/hosting/iclrgcmanager-interface.md).</span></span>  
  
- <span data-ttu-id="37d4c-111">IID_ICLRHostProtectionManager: especifica que `ppObject` será de tipo [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="37d4c-111">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-interface.md).</span></span>  
  
- <span data-ttu-id="37d4c-112">IID_ICLROnEventManager: especifica que `ppObject` será de tipo [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="37d4c-112">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](../../../../docs/framework/unmanaged-api/hosting/iclroneventmanager-interface.md).</span></span>  
  
- <span data-ttu-id="37d4c-113">IID_ICLRPolicyManager: especifica que `ppObject` será de tipo [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="37d4c-113">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](../../../../docs/framework/unmanaged-api/hosting/iclrpolicymanager-interface.md).</span></span>  
  
- <span data-ttu-id="37d4c-114">IID_ICLRTaskManager: especifica que `ppObject` será de tipo [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="37d4c-114">IID_ICLRTaskManager: Specifies that `ppObject` will be of type [ICLRTaskManager](../../../../docs/framework/unmanaged-api/hosting/iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="37d4c-115">enuncia Puntero de interfaz al administrador solicitado, o null si se solicitó un tipo de administrador no válido.</span><span class="sxs-lookup"><span data-stu-id="37d4c-115">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="37d4c-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="37d4c-116">Return Value</span></span>  
  
|<span data-ttu-id="37d4c-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="37d4c-117">HRESULT</span></span>|<span data-ttu-id="37d4c-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="37d4c-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="37d4c-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="37d4c-119">S_OK</span></span>|<span data-ttu-id="37d4c-120">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="37d4c-120">The method returned successfully.</span></span>|  
|<span data-ttu-id="37d4c-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="37d4c-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="37d4c-122">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="37d4c-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="37d4c-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="37d4c-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="37d4c-124">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="37d4c-124">The call timed out.</span></span>|  
|<span data-ttu-id="37d4c-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="37d4c-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="37d4c-126">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="37d4c-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="37d4c-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="37d4c-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="37d4c-128">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="37d4c-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="37d4c-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="37d4c-129">E_FAIL</span></span>|<span data-ttu-id="37d4c-130">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="37d4c-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="37d4c-131">Una vez que un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="37d4c-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="37d4c-132">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="37d4c-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="37d4c-133">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="37d4c-133">E_NOINTERFACE</span></span>|<span data-ttu-id="37d4c-134">No se admite el tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="37d4c-134">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="37d4c-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37d4c-135">Requirements</span></span>  
 <span data-ttu-id="37d4c-136">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37d4c-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37d4c-137">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="37d4c-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="37d4c-138">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="37d4c-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37d4c-139">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37d4c-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37d4c-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="37d4c-140">See also</span></span>

- [<span data-ttu-id="37d4c-141">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="37d4c-141">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
- [<span data-ttu-id="37d4c-142">IHostControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="37d4c-142">IHostControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostcontrol-interface.md)
