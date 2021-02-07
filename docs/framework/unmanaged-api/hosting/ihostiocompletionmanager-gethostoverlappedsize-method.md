---
description: 'Más información sobre: IHostIoCompletionManager:: Gethostoverlappedsize ((método)'
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
ms.openlocfilehash: 2a2ebe1da82c5702269b634eadfe98b72739e3df
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99708572"
---
# <a name="ihostiocompletionmanagergethostoverlappedsize-method"></a><span data-ttu-id="156dc-103">IHostIoCompletionManager::GetHostOverlappedSize (Método)</span><span class="sxs-lookup"><span data-stu-id="156dc-103">IHostIoCompletionManager::GetHostOverlappedSize Method</span></span>

<span data-ttu-id="156dc-104">Obtiene el tamaño de los datos personalizados que el host pretende anexar a las solicitudes de e/s.</span><span class="sxs-lookup"><span data-stu-id="156dc-104">Gets the size of any custom data the host intends to append to I/O requests.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="156dc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="156dc-105">Syntax</span></span>  
  
```cpp  
HRESULT GetHostOverlappedSize (  
    [out] DWORD *pcbSize  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="156dc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="156dc-106">Parameters</span></span>  

 `pcbSize`  
 <span data-ttu-id="156dc-107">enuncia Puntero al número de bytes que debe asignar el Common Language Runtime (CLR) además del tamaño del `OVERLAPPED` objeto Win32.</span><span class="sxs-lookup"><span data-stu-id="156dc-107">[out] A pointer to the number of bytes that the common language runtime (CLR) should allocate in addition to the size of the Win32 `OVERLAPPED` object.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="156dc-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="156dc-108">Return Value</span></span>  
  
|<span data-ttu-id="156dc-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="156dc-109">HRESULT</span></span>|<span data-ttu-id="156dc-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="156dc-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="156dc-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="156dc-111">S_OK</span></span>|<span data-ttu-id="156dc-112">`GetHostOverlappedSize` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="156dc-112">`GetHostOverlappedSize` returned successfully.</span></span>|  
|<span data-ttu-id="156dc-113">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="156dc-113">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="156dc-114">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="156dc-114">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="156dc-115">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="156dc-115">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="156dc-116">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="156dc-116">The call timed out.</span></span>|  
|<span data-ttu-id="156dc-117">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="156dc-117">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="156dc-118">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="156dc-118">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="156dc-119">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="156dc-119">HOST_E_ABANDONED</span></span>|<span data-ttu-id="156dc-120">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="156dc-120">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="156dc-121">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="156dc-121">E_FAIL</span></span>|<span data-ttu-id="156dc-122">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="156dc-122">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="156dc-123">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="156dc-123">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="156dc-124">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="156dc-124">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="156dc-125">Observaciones</span><span class="sxs-lookup"><span data-stu-id="156dc-125">Remarks</span></span>  

 <span data-ttu-id="156dc-126">Todas las llamadas de e/s asincrónicas a las API de la plataforma Windows toman un `OVERLAPPED` objeto Win32, que proporciona información como la posición del puntero de archivo.</span><span class="sxs-lookup"><span data-stu-id="156dc-126">All asynchronous I/O calls to Windows Platform APIs take a Win32 `OVERLAPPED` object, which provides information such as the file pointer position.</span></span> <span data-ttu-id="156dc-127">Para mantener el estado, las aplicaciones que realizan llamadas asincrónicas de e/s suelen agregar datos personalizados a la estructura.</span><span class="sxs-lookup"><span data-stu-id="156dc-127">To maintain state, applications that make asynchronous I/O calls typically add custom data to the structure.</span></span> <span data-ttu-id="156dc-128">`GetHostOverlappedSize` y [IHostIoCompletionManager:: initializehostoverlapped (](ihostiocompletionmanager-initializehostoverlapped-method.md) proporcionan una oportunidad para que el host incluya estos datos personalizados.</span><span class="sxs-lookup"><span data-stu-id="156dc-128">`GetHostOverlappedSize` and [IHostIoCompletionManager::InitializeHostOverlapped](ihostiocompletionmanager-initializehostoverlapped-method.md) provide an opportunity for the host to include such custom data.</span></span>  
  
 <span data-ttu-id="156dc-129">CLR llama al `GetHostOverlappedSize` método para determinar el tamaño de los datos personalizados que el host tiende a anexar al `OVERLAPPED` objeto.</span><span class="sxs-lookup"><span data-stu-id="156dc-129">The CLR calls the `GetHostOverlappedSize` method to determine the size of the custom data that the host intends to append to the `OVERLAPPED` object.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="156dc-130">`GetHostOverlappedSize` solo se llama una vez.</span><span class="sxs-lookup"><span data-stu-id="156dc-130">`GetHostOverlappedSize` is called only once.</span></span> <span data-ttu-id="156dc-131">Los datos personalizados del host deben tener el mismo tamaño para cada solicitud de e/s.</span><span class="sxs-lookup"><span data-stu-id="156dc-131">The host's custom data must be the same size for every I/O request.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="156dc-132">El tamaño del `OVERLAPPED` propio objeto no se incluye en el valor de `pcbSize` .</span><span class="sxs-lookup"><span data-stu-id="156dc-132">The size of the `OVERLAPPED` object itself is not included in the value of `pcbSize`.</span></span>  
  
 <span data-ttu-id="156dc-133">Para obtener más información acerca de la `OVERLAPPED` estructura, vea la documentación de la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="156dc-133">For more information about the `OVERLAPPED` structure, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="156dc-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="156dc-134">Requirements</span></span>  

 <span data-ttu-id="156dc-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="156dc-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="156dc-136">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="156dc-136">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="156dc-137">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="156dc-137">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="156dc-138">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="156dc-138">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="156dc-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="156dc-139">See also</span></span>

- <xref:System.Threading.NativeOverlapped>
- [<span data-ttu-id="156dc-140">ICLRIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="156dc-140">ICLRIoCompletionManager Interface</span></span>](iclriocompletionmanager-interface.md)
- [<span data-ttu-id="156dc-141">IHostIoCompletionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="156dc-141">IHostIoCompletionManager Interface</span></span>](ihostiocompletionmanager-interface.md)
