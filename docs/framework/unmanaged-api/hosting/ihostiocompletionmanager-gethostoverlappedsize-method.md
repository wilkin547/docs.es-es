---
title: IHostIoCompletionManager::GetHostOverlappedSize (Método)
ms.date: 03/30/2017
api_name:
- IHostIoCompletionManager.GetHostOverlappedSize
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize
helpviewer_keywords:
- IHostIoCompletionManager::GetHostOverlappedSize method [.NET Framework hosting]
- GetHostOverlappedSize method [.NET Framework hosting]
ms.assetid: 2902578b-d5e2-4f8d-a103-0c7b6dceda9e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 54e72205f8f976498df3b1fe1e055fb7df12d68e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67780682"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="30d13-102">IHostIoCompletionManager::GetHostOverlappedSize (Método)</span><span class="sxs-lookup"><span data-stu-id="30d13-102">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>
<span data-ttu-id="30d13-103">Obtiene el tamaño de los datos personalizados que el host pretende anexar a las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="30d13-103">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30d13-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="30d13-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="30d13-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="30d13-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="30d13-106">[out] Un puntero al número de bytes que common language runtime (CLR) debe asignar además del tamaño de Win32 `OVERLAPPED` objeto.</span><span class="sxs-lookup"><span data-stu-id="30d13-106">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="30d13-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="30d13-107">Return Value</span></span>  
  
|<span data-ttu-id="30d13-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="30d13-108">HRESULT</span></span>|<span data-ttu-id="30d13-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="30d13-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="30d13-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="30d13-110">S_OK</span></span>|<span data-ttu-id="30d13-111">`GetHostOverlappedSize` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="30d13-111">`GetHostOverlappedSize` returned successfully.</span></span>|  
|<span data-ttu-id="30d13-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="30d13-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="30d13-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="30d13-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="30d13-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="30d13-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="30d13-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="30d13-115">The call timed out.</span></span>|  
|<span data-ttu-id="30d13-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="30d13-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="30d13-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="30d13-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="30d13-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="30d13-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="30d13-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="30d13-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="30d13-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="30d13-120">E_FAIL</span></span>|<span data-ttu-id="30d13-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="30d13-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="30d13-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="30d13-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="30d13-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="30d13-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30d13-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="30d13-124">Remarks</span></span>  
 <span data-ttu-id="30d13-125">Todas las llamadas de E/S asincrónicas a las API de plataforma de Windows tome Win32 `OVERLAPPED` object, que proporciona información como la posición del puntero de archivo.</span><span class="sxs-lookup"><span data-stu-id="30d13-125">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="30d13-126">Para mantener el estado, las aplicaciones que realizan llamadas de E/S asincrónicas suelen agregan datos personalizados a la estructura.</span><span class="sxs-lookup"><span data-stu-id="30d13-126">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> <span data-ttu-id="30d13-127">`GetHostOverlappedSize` y [IHostIoCompletionManager:: InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) proporcionan una oportunidad para que el host incluir dichos datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="30d13-127">`GetHostOverlappedSize` and [IHostIoCompletionManager::InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="30d13-128">CLR llama a la `GetHostOverlappedSize` método para determinar el tamaño de los datos personalizados que el host pretende anexar a la `OVERLAPPED` objeto.</span><span class="sxs-lookup"><span data-stu-id="30d13-128">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="30d13-129">`GetHostOverlappedSize` se llama solo una vez.</span><span class="sxs-lookup"><span data-stu-id="30d13-129">`GetHostOverlappedSize` is called only once.</span></span> <span data-ttu-id="30d13-130">Datos personalizados del host deben ser el mismo tamaño para cada solicitud de E/S.</span><span class="sxs-lookup"><span data-stu-id="30d13-130">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="30d13-131">El tamaño de la `OVERLAPPED` propio objeto no se incluye en el valor de `pcbSize`.</span><span class="sxs-lookup"><span data-stu-id="30d13-131">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="30d13-132">Para obtener más información sobre la `OVERLAPPED` estructura, vea la documentación de la plataforma de Windows.</span><span class="sxs-lookup"><span data-stu-id="30d13-132">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="30d13-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30d13-133">Requirements</span></span>  
 <span data-ttu-id="30d13-134">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30d13-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30d13-135">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="30d13-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="30d13-136">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="30d13-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="30d13-137">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30d13-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30d13-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="30d13-138">See also</span></span>

- <xref:System.Threading.NativeOverlapped>
- [<span data-ttu-id="30d13-139">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="30d13-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="30d13-140">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="30d13-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
