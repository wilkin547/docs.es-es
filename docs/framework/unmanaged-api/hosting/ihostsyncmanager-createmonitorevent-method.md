---
title: IHostSyncManager::CreateMonitorEvent (Método)
ms.date: 03/30/2017
api_name:
- IHostSyncManager.CreateMonitorEvent
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostSyncManager::CreateMonitorEvent
helpviewer_keywords:
- CreateMonitorEvent method [.NET Framework hosting]
- IHostSyncManager::CreateMonitorEvent method [.NET Framework hosting]
ms.assetid: 524c7fd3-9b5c-46e7-99ba-555fd2fe33f0
topic_type:
- apiref
ms.openlocfilehash: c0f7e1fd6bf4c9386300b11477df85e87899fc67
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83803319"
---
# <a name="ihostsyncmanagercreatemonitorevent-method"></a><span data-ttu-id="4d2f0-102">IHostSyncManager::CreateMonitorEvent (Método)</span><span class="sxs-lookup"><span data-stu-id="4d2f0-102">IHostSyncManager::CreateMonitorEvent Method</span></span>
<span data-ttu-id="4d2f0-103">Crea un objeto de evento de restablecimiento automático supervisado.</span><span class="sxs-lookup"><span data-stu-id="4d2f0-103">Creates a monitored auto-reset event object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4d2f0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4d2f0-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateMonitorEvent (  
    [in]  SIZE_T cookie,  
    [out] IHostAutoEvent **ppEvent  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4d2f0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4d2f0-105">Parameters</span></span>  
 `cookie`  
 <span data-ttu-id="4d2f0-106">de Cookie que se va a asociar al objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="4d2f0-106">[in] A cookie to associate with the event object.</span></span>  
  
 `ppEvent`  
 <span data-ttu-id="4d2f0-107">enuncia Puntero a la dirección de una instancia de [IHostAutoEvent](ihostautoevent-interface.md) o null si no se pudo crear el objeto de evento.</span><span class="sxs-lookup"><span data-stu-id="4d2f0-107">[out] A pointer to the address of an [IHostAutoEvent](ihostautoevent-interface.md) instance, or null if the event object could not be created.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4d2f0-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4d2f0-108">Return Value</span></span>  
  
|<span data-ttu-id="4d2f0-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4d2f0-109">HRESULT</span></span>|<span data-ttu-id="4d2f0-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="4d2f0-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="4d2f0-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="4d2f0-111">S_OK</span></span>|<span data-ttu-id="4d2f0-112">`CreateMonitorEvent`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4d2f0-112">`CreateMonitorEvent` returned successfully.</span></span>|  
|<span data-ttu-id="4d2f0-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="4d2f0-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="4d2f0-114">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="4d2f0-114">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="4d2f0-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="4d2f0-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="4d2f0-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="4d2f0-116">The call timed out.</span></span>|  
|<span data-ttu-id="4d2f0-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="4d2f0-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="4d2f0-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="4d2f0-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="4d2f0-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="4d2f0-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="4d2f0-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="4d2f0-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="4d2f0-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="4d2f0-121">E_FAIL</span></span>|<span data-ttu-id="4d2f0-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="4d2f0-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="4d2f0-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="4d2f0-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="4d2f0-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="4d2f0-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="4d2f0-125">E_OUTOFMEMORY</span><span class="sxs-lookup"><span data-stu-id="4d2f0-125">E_OUTOFMEMORY</span></span>|<span data-ttu-id="4d2f0-126">No había suficiente memoria disponible para crear el objeto de evento solicitado.</span><span class="sxs-lookup"><span data-stu-id="4d2f0-126">Not enough memory was available to create the requested event object.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4d2f0-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4d2f0-127">Remarks</span></span>  
 <span data-ttu-id="4d2f0-128">`CreateMonitorEvent`Devuelve un `IHostAutoEvent` que CLR usa en su implementación del <xref:System.Threading.Monitor?displayProperty=nameWithType> tipo administrado.</span><span class="sxs-lookup"><span data-stu-id="4d2f0-128">`CreateMonitorEvent` returns an `IHostAutoEvent` that the CLR uses in its implementation of the managed <xref:System.Threading.Monitor?displayProperty=nameWithType> type.</span></span> <span data-ttu-id="4d2f0-129">Este método refleja la `CreateEvent` función de Win32, con un valor de `false` especificado para el `bManualReset` parámetro.</span><span class="sxs-lookup"><span data-stu-id="4d2f0-129">This method mirrors the Win32 `CreateEvent` function, with a value of `false` specified for the `bManualReset` parameter.</span></span>  
  
 <span data-ttu-id="4d2f0-130">El host puede usar la cookie para determinar qué tarea está esperando en el monitor llamando al método [ICLRSyncManager:: GetMonitorOwner (](iclrsyncmanager-getmonitorowner-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4d2f0-130">The host can use the cookie to determine which task is waiting on the monitor by calling the [ICLRSyncManager::GetMonitorOwner](iclrsyncmanager-getmonitorowner-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4d2f0-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4d2f0-131">Requirements</span></span>  
 <span data-ttu-id="4d2f0-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4d2f0-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4d2f0-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="4d2f0-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="4d2f0-134">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="4d2f0-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="4d2f0-135">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4d2f0-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4d2f0-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="4d2f0-136">See also</span></span>

- [<span data-ttu-id="4d2f0-137">ICLRSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d2f0-137">ICLRSyncManager Interface</span></span>](iclrsyncmanager-interface.md)
- [<span data-ttu-id="4d2f0-138">IHostAutoEvent (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d2f0-138">IHostAutoEvent Interface</span></span>](ihostautoevent-interface.md)
- [<span data-ttu-id="4d2f0-139">IHostSyncManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4d2f0-139">IHostSyncManager Interface</span></span>](ihostsyncmanager-interface.md)
- <xref:System.Threading.Monitor>
