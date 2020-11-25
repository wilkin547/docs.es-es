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
ms.openlocfilehash: d18b3a5c06ac0d3a86f7823f3b140c76c6c9a746
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728360"
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="ffc18-102">ICLRControl::GetCLRManager (Método)</span><span class="sxs-lookup"><span data-stu-id="ffc18-102">ICLRControl::GetCLRManager Method</span></span>

<span data-ttu-id="ffc18-103">Obtiene un puntero de interfaz a una instancia de cualquiera de los tipos de administrador que el host puede usar para configurar el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="ffc18-103">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ffc18-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ffc18-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ffc18-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ffc18-105">Parameters</span></span>  

 `riid`  
 <span data-ttu-id="ffc18-106">de `IID` Del tipo de administrador que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="ffc18-106">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="ffc18-107">`IID`Se admiten los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="ffc18-107">The following `IID` values are supported.</span></span>  
  
- <span data-ttu-id="ffc18-108">IID_ICLRDebugManager: especifica que será `ppObject` de tipo [ICLRDebugManager](iclrdebugmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ffc18-108">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](iclrdebugmanager-interface.md).</span></span>  
  
- <span data-ttu-id="ffc18-109">IID_ICLRErrorReportingManager: especifica que será `ppObject` de tipo [ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ffc18-109">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md).</span></span>  
  
- <span data-ttu-id="ffc18-110">IID_ICLRGCManager: especifica que será `ppObject` de tipo [ICLRGCManager](iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ffc18-110">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](iclrgcmanager-interface.md).</span></span>  
  
- <span data-ttu-id="ffc18-111">IID_ICLRHostProtectionManager: especifica que será `ppObject` de tipo [ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ffc18-111">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md).</span></span>  
  
- <span data-ttu-id="ffc18-112">IID_ICLROnEventManager: especifica que será `ppObject` de tipo [ICLROnEventManager](iclroneventmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ffc18-112">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](iclroneventmanager-interface.md).</span></span>  
  
- <span data-ttu-id="ffc18-113">IID_ICLRPolicyManager: especifica que `ppObject` será de tipo [ICLRPolicyManager](iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ffc18-113">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](iclrpolicymanager-interface.md).</span></span>  
  
- <span data-ttu-id="ffc18-114">IID_ICLRTaskManager: especifica que será `ppObject` de tipo [ICLRTaskManager](iclrtaskmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="ffc18-114">IID_ICLRTaskManager: Specifies that `ppObject` will be of type [ICLRTaskManager](iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="ffc18-115">enuncia Puntero de interfaz al administrador solicitado, o null si se solicitó un tipo de administrador no válido.</span><span class="sxs-lookup"><span data-stu-id="ffc18-115">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ffc18-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ffc18-116">Return Value</span></span>  
  
|<span data-ttu-id="ffc18-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ffc18-117">HRESULT</span></span>|<span data-ttu-id="ffc18-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="ffc18-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ffc18-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="ffc18-119">S_OK</span></span>|<span data-ttu-id="ffc18-120">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ffc18-120">The method returned successfully.</span></span>|  
|<span data-ttu-id="ffc18-121">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ffc18-121">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ffc18-122">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ffc18-122">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ffc18-123">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ffc18-123">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ffc18-124">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ffc18-124">The call timed out.</span></span>|  
|<span data-ttu-id="ffc18-125">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ffc18-125">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ffc18-126">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ffc18-126">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ffc18-127">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ffc18-127">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ffc18-128">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="ffc18-128">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ffc18-129">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ffc18-129">E_FAIL</span></span>|<span data-ttu-id="ffc18-130">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="ffc18-130">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ffc18-131">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ffc18-131">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ffc18-132">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ffc18-132">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="ffc18-133">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="ffc18-133">E_NOINTERFACE</span></span>|<span data-ttu-id="ffc18-134">No se admite el tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="ffc18-134">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ffc18-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ffc18-135">Requirements</span></span>  

 <span data-ttu-id="ffc18-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ffc18-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ffc18-137">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ffc18-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ffc18-138">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ffc18-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ffc18-139">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ffc18-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ffc18-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ffc18-140">See also</span></span>

- [<span data-ttu-id="ffc18-141">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ffc18-141">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="ffc18-142">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ffc18-142">IHostControl Interface</span></span>](ihostcontrol-interface.md)
