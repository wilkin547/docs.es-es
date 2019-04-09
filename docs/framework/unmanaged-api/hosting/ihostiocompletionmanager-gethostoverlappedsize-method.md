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
ms.openlocfilehash: e4a5661128765cc058417fef6373767d46a4bd7b
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59111805"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="9ab61-102">IHostIoCompletionManager::GetHostOverlappedSize (Método)</span><span class="sxs-lookup"><span data-stu-id="9ab61-102">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>
<span data-ttu-id="9ab61-103">Obtiene el tamaño de los datos personalizados que el host pretende anexar a las solicitudes de E/S.</span><span class="sxs-lookup"><span data-stu-id="9ab61-103">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9ab61-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9ab61-104">Syntax</span></span>  
  
```  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9ab61-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9ab61-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="9ab61-106">[out] Un puntero al número de bytes que common language runtime (CLR) debe asignar además del tamaño de Win32 `OVERLAPPED` objeto.</span><span class="sxs-lookup"><span data-stu-id="9ab61-106">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9ab61-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9ab61-107">Return Value</span></span>  
  
|<span data-ttu-id="9ab61-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9ab61-108">HRESULT</span></span>|<span data-ttu-id="9ab61-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="9ab61-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="9ab61-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="9ab61-110">S_OK</span></span>|`GetHostOverlappedSize` <span data-ttu-id="9ab61-111">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="9ab61-111">returned successfully.</span></span>|  
|<span data-ttu-id="9ab61-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="9ab61-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="9ab61-113">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="9ab61-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="9ab61-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="9ab61-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="9ab61-115">La llamada ha agotado el tiempo de espera.</span><span class="sxs-lookup"><span data-stu-id="9ab61-115">The call timed out.</span></span>|  
|<span data-ttu-id="9ab61-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="9ab61-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="9ab61-117">El llamador no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="9ab61-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="9ab61-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="9ab61-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="9ab61-119">Se canceló un evento mientras un subproceso bloqueado o fibra estaba esperando en ella.</span><span class="sxs-lookup"><span data-stu-id="9ab61-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="9ab61-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="9ab61-120">E_FAIL</span></span>|<span data-ttu-id="9ab61-121">Se ha producido un error irrecuperable desconocido.</span><span class="sxs-lookup"><span data-stu-id="9ab61-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="9ab61-122">Cuando un método devuelve E_FAIL, CLR ya no es utilizable dentro del proceso.</span><span class="sxs-lookup"><span data-stu-id="9ab61-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="9ab61-123">Las llamadas posteriores a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="9ab61-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9ab61-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9ab61-124">Remarks</span></span>  
 <span data-ttu-id="9ab61-125">Todas las llamadas de E/S asincrónicas a las API de plataforma de Windows tome Win32 `OVERLAPPED` object, que proporciona información como la posición del puntero de archivo.</span><span class="sxs-lookup"><span data-stu-id="9ab61-125">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="9ab61-126">Para mantener el estado, las aplicaciones que realizan llamadas de E/S asincrónicas suelen agregan datos personalizados a la estructura.</span><span class="sxs-lookup"><span data-stu-id="9ab61-126">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> `GetHostOverlappedSize` <span data-ttu-id="9ab61-127">y [IHostIoCompletionManager:: InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) proporcionan una oportunidad para que el host incluir dichos datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="9ab61-127">and [IHostIoCompletionManager::InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="9ab61-128">CLR llama a la `GetHostOverlappedSize` método para determinar el tamaño de los datos personalizados que el host pretende anexar a la `OVERLAPPED` objeto.</span><span class="sxs-lookup"><span data-stu-id="9ab61-128">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
>  `GetHostOverlappedSize` <span data-ttu-id="9ab61-129">se llama solo una vez.</span><span class="sxs-lookup"><span data-stu-id="9ab61-129">is called only once.</span></span> <span data-ttu-id="9ab61-130">Datos personalizados del host deben ser el mismo tamaño para cada solicitud de E/S.</span><span class="sxs-lookup"><span data-stu-id="9ab61-130">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="9ab61-131">El tamaño de la `OVERLAPPED` propio objeto no se incluye en el valor de `pcbSize`.</span><span class="sxs-lookup"><span data-stu-id="9ab61-131">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="9ab61-132">Para obtener más información sobre la `OVERLAPPED` estructura, vea la documentación de la plataforma de Windows.</span><span class="sxs-lookup"><span data-stu-id="9ab61-132">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9ab61-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9ab61-133">Requirements</span></span>  
 <span data-ttu-id="9ab61-134">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9ab61-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9ab61-135">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="9ab61-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="9ab61-136">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9ab61-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="9ab61-137">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="9ab61-137">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="9ab61-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="9ab61-138">See also</span></span>

- <xref:System.Threading.NativeOverlapped>
- [<span data-ttu-id="9ab61-139">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9ab61-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="9ab61-140">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="9ab61-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
