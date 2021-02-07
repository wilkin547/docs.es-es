---
description: 'Más información acerca de: ICLRControl:: GetCLRManager ((método)'
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
ms.openlocfilehash: fc24cbdfd4bebfff5c2f8d73a9cd6961a8c94e94
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99716723"
---
# <a name="iclrcontrolgetclrmanager-method"></a><span data-ttu-id="a7b16-103">ICLRControl::GetCLRManager (Método)</span><span class="sxs-lookup"><span data-stu-id="a7b16-103">ICLRControl::GetCLRManager Method</span></span>

<span data-ttu-id="a7b16-104">Obtiene un puntero de interfaz a una instancia de cualquiera de los tipos de administrador que el host puede usar para configurar el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a7b16-104">Gets an interface pointer to an instance of any of the manager types the host can use to configure the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7b16-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a7b16-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCLRManager (  
    [in]  REFIID  riid,  
    [out] void  **ppObject  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7b16-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a7b16-106">Parameters</span></span>  

 `riid`  
 <span data-ttu-id="a7b16-107">de `IID` Del tipo de administrador que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="a7b16-107">[in] The `IID` of the manager type to return.</span></span> <span data-ttu-id="a7b16-108">`IID`Se admiten los valores siguientes.</span><span class="sxs-lookup"><span data-stu-id="a7b16-108">The following `IID` values are supported.</span></span>  
  
- <span data-ttu-id="a7b16-109">IID_ICLRDebugManager: especifica que será `ppObject` de tipo [ICLRDebugManager](iclrdebugmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a7b16-109">IID_ICLRDebugManager: Specifies that `ppObject` will be of type [ICLRDebugManager](iclrdebugmanager-interface.md).</span></span>  
  
- <span data-ttu-id="a7b16-110">IID_ICLRErrorReportingManager: especifica que será `ppObject` de tipo [ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a7b16-110">IID_ICLRErrorReportingManager: Specifies that `ppObject` will be of type [ICLRErrorReportingManager](iclrerrorreportingmanager-interface.md).</span></span>  
  
- <span data-ttu-id="a7b16-111">IID_ICLRGCManager: especifica que será `ppObject` de tipo [ICLRGCManager](iclrgcmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a7b16-111">IID_ICLRGCManager: Specifies that `ppObject` will be of type [ICLRGCManager](iclrgcmanager-interface.md).</span></span>  
  
- <span data-ttu-id="a7b16-112">IID_ICLRHostProtectionManager: especifica que será `ppObject` de tipo [ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a7b16-112">IID_ICLRHostProtectionManager: Specifies that `ppObject` will be of type [ICLRHostProtectionManager](iclrhostprotectionmanager-interface.md).</span></span>  
  
- <span data-ttu-id="a7b16-113">IID_ICLROnEventManager: especifica que será `ppObject` de tipo [ICLROnEventManager](iclroneventmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a7b16-113">IID_ICLROnEventManager: Specifies that `ppObject` will be of type [ICLROnEventManager](iclroneventmanager-interface.md).</span></span>  
  
- <span data-ttu-id="a7b16-114">IID_ICLRPolicyManager: especifica que `ppObject` será de tipo [ICLRPolicyManager](iclrpolicymanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a7b16-114">IID_ICLRPolicyManager: Specifies that `ppObject` will be of type [ICLRPolicyManager](iclrpolicymanager-interface.md).</span></span>  
  
- <span data-ttu-id="a7b16-115">IID_ICLRTaskManager: especifica que será `ppObject` de tipo [ICLRTaskManager](iclrtaskmanager-interface.md).</span><span class="sxs-lookup"><span data-stu-id="a7b16-115">IID_ICLRTaskManager: Specifies that `ppObject` will be of type [ICLRTaskManager](iclrtaskmanager-interface.md).</span></span>  
  
 `ppObject`  
 <span data-ttu-id="a7b16-116">enuncia Puntero de interfaz al administrador solicitado, o null si se solicitó un tipo de administrador no válido.</span><span class="sxs-lookup"><span data-stu-id="a7b16-116">[out] An interface pointer to the requested manager, or null, if an invalid manager type was requested.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="a7b16-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a7b16-117">Return Value</span></span>  
  
|<span data-ttu-id="a7b16-118">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a7b16-118">HRESULT</span></span>|<span data-ttu-id="a7b16-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7b16-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a7b16-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="a7b16-120">S_OK</span></span>|<span data-ttu-id="a7b16-121">El método se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="a7b16-121">The method returned successfully.</span></span>|  
|<span data-ttu-id="a7b16-122">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a7b16-122">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a7b16-123">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a7b16-123">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="a7b16-124">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="a7b16-124">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="a7b16-125">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="a7b16-125">The call timed out.</span></span>|  
|<span data-ttu-id="a7b16-126">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="a7b16-126">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="a7b16-127">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="a7b16-127">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="a7b16-128">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="a7b16-128">HOST_E_ABANDONED</span></span>|<span data-ttu-id="a7b16-129">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="a7b16-129">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="a7b16-130">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a7b16-130">E_FAIL</span></span>|<span data-ttu-id="a7b16-131">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a7b16-131">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="a7b16-132">Después de que un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a7b16-132">After a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="a7b16-133">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a7b16-133">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a7b16-134">E_NOINTERFACE</span><span class="sxs-lookup"><span data-stu-id="a7b16-134">E_NOINTERFACE</span></span>|<span data-ttu-id="a7b16-135">No se admite el tipo de interfaz.</span><span class="sxs-lookup"><span data-stu-id="a7b16-135">The interface type is not supported.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7b16-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7b16-136">Requirements</span></span>  

 <span data-ttu-id="a7b16-137">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7b16-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7b16-138">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a7b16-138">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7b16-139">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7b16-139">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7b16-140">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7b16-140">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7b16-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7b16-141">See also</span></span>

- [<span data-ttu-id="a7b16-142">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7b16-142">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
- [<span data-ttu-id="a7b16-143">IHostControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7b16-143">IHostControl Interface</span></span>](ihostcontrol-interface.md)
