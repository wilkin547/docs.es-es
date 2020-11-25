---
title: IHostMemoryManager::VirtualQuery (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualQuery
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualQuery
helpviewer_keywords:
- IHostMemoryManager::VirtualQuery method [.NET Framework hosting]
- VirtualQuery method [.NET Framework hosting]
ms.assetid: 757af1e6-b9e8-49e7-b5db-342be3aa205f
topic_type:
- apiref
ms.openlocfilehash: 6e3cb5bcec831f143d45f733c9e2f977390aade6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731252"
---
# <a name="ihostmemorymanagervirtualquery-method"></a><span data-ttu-id="ecbaa-102">IHostMemoryManager::VirtualQuery (Método)</span><span class="sxs-lookup"><span data-stu-id="ecbaa-102">IHostMemoryManager::VirtualQuery Method</span></span>

<span data-ttu-id="ecbaa-103">Actúa como un contenedor lógico para la función de Win32 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="ecbaa-104">La implementación de Win32 de `VirtualQuery` recupera información sobre un intervalo de páginas en el espacio de direcciones virtuales del proceso de llamada.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-104">The Win32 implementation of `VirtualQuery` retrieves information about a range of pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ecbaa-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ecbaa-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualQuery (  
    [in]  void*    lpAddress,  
    [out] void*    lpBuffer,  
    [in]  SIZE_T   dwLength,  
    [out] SIZE_T*  pResult  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ecbaa-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ecbaa-106">Parameters</span></span>  

 `lpAddress`  
 <span data-ttu-id="ecbaa-107">de Puntero a la dirección de la memoria virtual que se va a consultar.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-107">[in] A pointer to the address in virtual memory to be queried.</span></span>  
  
 `lpBuffer`  
 <span data-ttu-id="ecbaa-108">enuncia Puntero a una estructura que contiene información sobre la región de memoria especificada.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-108">[out] A pointer to a structure that contains information about the specified memory region.</span></span>  
  
 `dwLength`  
 <span data-ttu-id="ecbaa-109">de Tamaño, en bytes, del búfer `lpBuffer` al que apunta.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-109">[in] The size, in bytes, of the buffer that `lpBuffer` points to.</span></span>  
  
 `pResult`  
 <span data-ttu-id="ecbaa-110">enuncia Puntero al número de bytes devuelto por el búfer de información.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-110">[out] A pointer to the number of bytes returned by the information buffer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="ecbaa-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ecbaa-111">Return Value</span></span>  
  
|<span data-ttu-id="ecbaa-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="ecbaa-112">HRESULT</span></span>|<span data-ttu-id="ecbaa-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="ecbaa-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="ecbaa-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="ecbaa-114">S_OK</span></span>|<span data-ttu-id="ecbaa-115">`VirtualQuery` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-115">`VirtualQuery` returned successfully.</span></span>|  
|<span data-ttu-id="ecbaa-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="ecbaa-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="ecbaa-117">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="ecbaa-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="ecbaa-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="ecbaa-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-119">The call timed out.</span></span>|  
|<span data-ttu-id="ecbaa-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="ecbaa-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="ecbaa-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="ecbaa-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="ecbaa-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="ecbaa-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="ecbaa-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="ecbaa-124">E_FAIL</span></span>|<span data-ttu-id="ecbaa-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="ecbaa-126">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="ecbaa-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="ecbaa-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ecbaa-128">Remarks</span></span>  

 <span data-ttu-id="ecbaa-129">`VirtualQuery` proporciona información sobre un intervalo de páginas en el espacio de direcciones virtuales del proceso de llamada.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-129">`VirtualQuery` provides information about a range of pages in the virtual address space of the calling process.</span></span> <span data-ttu-id="ecbaa-130">Esta implementación establece el valor del `pResult` parámetro en el número de bytes devuelto en el búfer de información y devuelve un valor HRESULT.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-130">This implementation sets the value of the `pResult` parameter to the number of bytes returned in the information buffer, and returns an HRESULT value.</span></span> <span data-ttu-id="ecbaa-131">En la función de Win32 `VirtualQuery` , el valor devuelto es el tamaño del búfer.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-131">In the Win32 `VirtualQuery` function, the return value is the buffer size.</span></span> <span data-ttu-id="ecbaa-132">Para obtener más información, vea la documentación de la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-132">For more information, see the Windows Platform documentation.</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="ecbaa-133">La implementación del sistema operativo de no `VirtualQuery` incurre en un interbloqueo y puede ejecutarse hasta completarse con subprocesos aleatorios suspendidos en el código de usuario.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-133">The operating system's implementation of `VirtualQuery` does not incur deadlock and can run to completion with random threads suspended in user code.</span></span> <span data-ttu-id="ecbaa-134">Tenga mucho cuidado al implementar una versión hospedada de este método.</span><span class="sxs-lookup"><span data-stu-id="ecbaa-134">Use great caution when implementing a hosted version of this method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ecbaa-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ecbaa-135">Requirements</span></span>  

 <span data-ttu-id="ecbaa-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ecbaa-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ecbaa-137">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="ecbaa-137">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="ecbaa-138">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ecbaa-138">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="ecbaa-139">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ecbaa-139">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ecbaa-140">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ecbaa-140">See also</span></span>

- [<span data-ttu-id="ecbaa-141">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ecbaa-141">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
