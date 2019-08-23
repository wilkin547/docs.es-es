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
ms.openlocfilehash: c43f906961b9e76d5f0f34ba5a5b2f656f5b1488
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/22/2019
ms.locfileid: "69937514"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="d678a-102">IHostIoCompletionManager::GetHostOverlappedSize (Método)</span><span class="sxs-lookup"><span data-stu-id="d678a-102">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>
<span data-ttu-id="d678a-103">Obtiene el tamaño de los datos personalizados que el host pretende anexar a las solicitudes de e/s.</span><span class="sxs-lookup"><span data-stu-id="d678a-103">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d678a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d678a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d678a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d678a-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="d678a-106">enuncia Puntero al número de bytes que debe asignar el Common Language Runtime (CLR) además del tamaño del objeto Win32 `OVERLAPPED` .</span><span class="sxs-lookup"><span data-stu-id="d678a-106">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d678a-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d678a-107">Return Value</span></span>  
  
|<span data-ttu-id="d678a-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d678a-108">HRESULT</span></span>|<span data-ttu-id="d678a-109">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="d678a-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d678a-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="d678a-110">S_OK</span></span>|<span data-ttu-id="d678a-111">`GetHostOverlappedSize`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d678a-111">`GetHostOverlappedSize` returned successfully.</span></span>|  
|<span data-ttu-id="d678a-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d678a-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d678a-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d678a-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d678a-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d678a-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d678a-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d678a-115">The call timed out.</span></span>|  
|<span data-ttu-id="d678a-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d678a-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d678a-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d678a-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d678a-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d678a-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d678a-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="d678a-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d678a-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d678a-120">E_FAIL</span></span>|<span data-ttu-id="d678a-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="d678a-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d678a-122">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="d678a-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d678a-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d678a-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d678a-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d678a-124">Remarks</span></span>  
 <span data-ttu-id="d678a-125">Todas las llamadas de e/s asincrónicas a las API de la `OVERLAPPED` plataforma Windows toman un objeto Win32, que proporciona información como la posición del puntero de archivo.</span><span class="sxs-lookup"><span data-stu-id="d678a-125">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="d678a-126">Para mantener el estado, las aplicaciones que realizan llamadas asincrónicas de e/s suelen agregar datos personalizados a la estructura.</span><span class="sxs-lookup"><span data-stu-id="d678a-126">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> <span data-ttu-id="d678a-127">`GetHostOverlappedSize`y [IHostIoCompletionManager:: initializehostoverlapped (](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) proporcionan una oportunidad para que el host incluya estos datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="d678a-127">`GetHostOverlappedSize` and [IHostIoCompletionManager::InitializeHostOverlapped](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="d678a-128">CLR llama `GetHostOverlappedSize` al método para determinar el tamaño de los datos personalizados que el host tiende a anexar `OVERLAPPED` al objeto.</span><span class="sxs-lookup"><span data-stu-id="d678a-128">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d678a-129">`GetHostOverlappedSize`solo se llama una vez.</span><span class="sxs-lookup"><span data-stu-id="d678a-129">`GetHostOverlappedSize` is called only once.</span></span> <span data-ttu-id="d678a-130">Los datos personalizados del host deben tener el mismo tamaño para cada solicitud de e/s.</span><span class="sxs-lookup"><span data-stu-id="d678a-130">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="d678a-131">El tamaño del `OVERLAPPED` propio objeto no se incluye en el valor de `pcbSize`.</span><span class="sxs-lookup"><span data-stu-id="d678a-131">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="d678a-132">Para obtener más información acerca `OVERLAPPED` de la estructura, vea la documentación de la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="d678a-132">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d678a-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d678a-133">Requirements</span></span>  
 <span data-ttu-id="d678a-134">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d678a-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d678a-135">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="d678a-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d678a-136">**Biblioteca** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d678a-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d678a-137">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d678a-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d678a-138">Vea también</span><span class="sxs-lookup"><span data-stu-id="d678a-138">See also</span></span>

- <xref:System.Threading.NativeOverlapped>
- [<span data-ttu-id="d678a-139">ICLRIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d678a-139">ICLRIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclriocompletionmanager-interface.md)
- [<span data-ttu-id="d678a-140">IHostIoCompletionManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d678a-140">IHostIoCompletionManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostiocompletionmanager-interface.md)
