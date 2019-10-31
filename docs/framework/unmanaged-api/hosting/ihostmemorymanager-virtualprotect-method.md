---
title: IHostMemoryManager::VirtualProtect (Método)
ms.date: 03/30/2017
api_name:
- IHostMemoryManager.VirtualProtect
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IHostMemoryManager::VirtualProtect
helpviewer_keywords:
- IHostMemoryManager::VirtualProtect method [.NET Framework hosting]
- VirtualProtect method [.NET Framework hosting]
ms.assetid: 13be0299-df0d-4951-aabf-0676a30b385f
topic_type:
- apiref
ms.openlocfilehash: d39ad45e143026f40ffcf1339e923837f9e812c4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73195856"
---
# <a name="ihostmemorymanagervirtualprotect-method"></a><span data-ttu-id="d6dae-102">IHostMemoryManager::VirtualProtect (Método)</span><span class="sxs-lookup"><span data-stu-id="d6dae-102">IHostMemoryManager::VirtualProtect Method</span></span>
<span data-ttu-id="d6dae-103">Actúa como un contenedor lógico para la función de Win32 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="d6dae-103">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="d6dae-104">La implementación de Win32 de `VirtualProtect` cambia la protección en una región de páginas confirmadas en el espacio de direcciones virtuales del proceso de llamada.</span><span class="sxs-lookup"><span data-stu-id="d6dae-104">The Win32 implementation of `VirtualProtect` changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6dae-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6dae-105">Syntax</span></span>  
  
```cpp  
HRESULT VirtualProtect (  
    [in]  void*   lpAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flNewProtect,  
    [out] DWORD*  pflOldProtect  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d6dae-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d6dae-106">Parameters</span></span>  
 `lpAddress`  
 <span data-ttu-id="d6dae-107">de Puntero a la dirección base de la memoria virtual cuyos atributos de protección se van a cambiar.</span><span class="sxs-lookup"><span data-stu-id="d6dae-107">[in] A pointer to the base address of the virtual memory whose protection attributes are to be changed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="d6dae-108">de Tamaño, en bytes, del área de páginas de memoria que se va a cambiar.</span><span class="sxs-lookup"><span data-stu-id="d6dae-108">[in] The size, in bytes, of the region of memory pages to be changed.</span></span>  
  
 `flNewProtect`  
 <span data-ttu-id="d6dae-109">de El tipo de protección de memoria que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="d6dae-109">[in] The type of memory protection to apply.</span></span>  
  
 `pflOldProtect`  
 <span data-ttu-id="d6dae-110">enuncia Puntero al valor de protección de memoria anterior.</span><span class="sxs-lookup"><span data-stu-id="d6dae-110">[out] A pointer to the previous memory protection value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="d6dae-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="d6dae-111">Return Value</span></span>  
  
|<span data-ttu-id="d6dae-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="d6dae-112">HRESULT</span></span>|<span data-ttu-id="d6dae-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6dae-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="d6dae-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="d6dae-114">S_OK</span></span>|<span data-ttu-id="d6dae-115">`VirtualProtect` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="d6dae-115">`VirtualProtect` returned successfully.</span></span>|  
|<span data-ttu-id="d6dae-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="d6dae-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="d6dae-117">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="d6dae-117">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="d6dae-118">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d6dae-118">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="d6dae-119">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="d6dae-119">The call timed out.</span></span>|  
|<span data-ttu-id="d6dae-120">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="d6dae-120">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="d6dae-121">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="d6dae-121">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="d6dae-122">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="d6dae-122">HOST_E_ABANDONED</span></span>|<span data-ttu-id="d6dae-123">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="d6dae-123">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="d6dae-124">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="d6dae-124">E_FAIL</span></span>|<span data-ttu-id="d6dae-125">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="d6dae-125">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="d6dae-126">Cuando un método devuelve E_FAIL, el CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="d6dae-126">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="d6dae-127">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="d6dae-127">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d6dae-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d6dae-128">Remarks</span></span>  
 <span data-ttu-id="d6dae-129">Esta implementación de `VirtualProtect` devuelve un valor HRESULT, mientras que la implementación de Win32 devuelve un valor distinto de cero para indicar que se ha realizado correctamente y un valor de cero para indicar el error.</span><span class="sxs-lookup"><span data-stu-id="d6dae-129">This implementation of `VirtualProtect` returns an HRESULT value, while the Win32 implementation returns a non-zero value to indicate success, and a zero value to indicate failure.</span></span> <span data-ttu-id="d6dae-130">Para obtener más información, vea la documentación de la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="d6dae-130">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d6dae-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6dae-131">Requirements</span></span>  
 <span data-ttu-id="d6dae-132">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6dae-132">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6dae-133">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d6dae-133">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d6dae-134">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d6dae-134">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d6dae-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6dae-135">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6dae-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="d6dae-136">See also</span></span>

- [<span data-ttu-id="d6dae-137">IHostMemoryManager (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d6dae-137">IHostMemoryManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/ihostmemorymanager-interface.md)
