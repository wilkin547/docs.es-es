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
ms.openlocfilehash: a97009a4ebc834d867dddcc350033c550364ea42
ms.sourcegitcommit: d223616e7e6fe2139079052e6fcbe25413fb9900
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/22/2020
ms.locfileid: "83804745"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="6fba1-102">IHostIoCompletionManager::GetHostOverlappedSize (Método)</span><span class="sxs-lookup"><span data-stu-id="6fba1-102">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>
<span data-ttu-id="6fba1-103">Obtiene el tamaño de los datos personalizados que el host pretende anexar a las solicitudes de e/s.</span><span class="sxs-lookup"><span data-stu-id="6fba1-103">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6fba1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6fba1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6fba1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6fba1-105">Parameters</span></span>  
 `pcbSize`  
 <span data-ttu-id="6fba1-106">enuncia Puntero al número de bytes que debe asignar el Common Language Runtime (CLR) además del tamaño del `OVERLAPPED` objeto Win32.</span><span class="sxs-lookup"><span data-stu-id="6fba1-106">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6fba1-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6fba1-107">Return Value</span></span>  
  
|<span data-ttu-id="6fba1-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6fba1-108">HRESULT</span></span>|<span data-ttu-id="6fba1-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="6fba1-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6fba1-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="6fba1-110">S_OK</span></span>|<span data-ttu-id="6fba1-111">`GetHostOverlappedSize`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="6fba1-111">`GetHostOverlappedSize` returned successfully.</span></span>|  
|<span data-ttu-id="6fba1-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="6fba1-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="6fba1-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="6fba1-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="6fba1-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="6fba1-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="6fba1-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="6fba1-115">The call timed out.</span></span>|  
|<span data-ttu-id="6fba1-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="6fba1-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="6fba1-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="6fba1-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="6fba1-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="6fba1-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="6fba1-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="6fba1-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="6fba1-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="6fba1-120">E_FAIL</span></span>|<span data-ttu-id="6fba1-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="6fba1-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="6fba1-122">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="6fba1-122">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="6fba1-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="6fba1-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6fba1-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="6fba1-124">Remarks</span></span>  
 <span data-ttu-id="6fba1-125">Todas las llamadas de e/s asincrónicas a las API de la plataforma Windows toman un `OVERLAPPED` objeto Win32, que proporciona información como la posición del puntero de archivo.</span><span class="sxs-lookup"><span data-stu-id="6fba1-125">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="6fba1-126">Para mantener el estado, las aplicaciones que realizan llamadas asincrónicas de e/s suelen agregar datos personalizados a la estructura.</span><span class="sxs-lookup"><span data-stu-id="6fba1-126">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> <span data-ttu-id="6fba1-127">`GetHostOverlappedSize`y [IHostIoCompletionManager:: initializehostoverlapped (](ihostiocompletionmanager-initializehostoverlapped-method.md) proporcionan una oportunidad para que el host incluya estos datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="6fba1-127">`GetHostOverlappedSize` and [IHostIoCompletionManager::InitializeHostOverlapped](ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="6fba1-128">CLR llama al `GetHostOverlappedSize` método para determinar el tamaño de los datos personalizados que el host tiende a anexar al `OVERLAPPED` objeto.</span><span class="sxs-lookup"><span data-stu-id="6fba1-128">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="6fba1-129">`GetHostOverlappedSize`solo se llama una vez.</span><span class="sxs-lookup"><span data-stu-id="6fba1-129">`GetHostOverlappedSize` is called only once.</span></span> <span data-ttu-id="6fba1-130">Los datos personalizados del host deben tener el mismo tamaño para cada solicitud de e/s.</span><span class="sxs-lookup"><span data-stu-id="6fba1-130">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="6fba1-131">El tamaño del `OVERLAPPED` propio objeto no se incluye en el valor de `pcbSize` .</span><span class="sxs-lookup"><span data-stu-id="6fba1-131">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="6fba1-132">Para obtener más información acerca de la `OVERLAPPED` estructura, vea la documentación de la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="6fba1-132">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6fba1-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6fba1-133">Requirements</span></span>  
 <span data-ttu-id="6fba1-134">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6fba1-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6fba1-135">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="6fba1-135">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6fba1-136">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6fba1-136">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6fba1-137">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6fba1-137">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6fba1-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="6fba1-138">See also</span></span>

- <xref:System.Threading.NativeOverlapped>
- [<span data-ttu-id="6fba1-139">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6fba1-139">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="6fba1-140">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="6fba1-140">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
