---
description: 'Más información acerca de: IHostMemoryManager:: VirtualProtect ((método)'
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
ms.openlocfilehash: 66e1fb5afdc3aa5c400ed0ffa9cea569d300e6a3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99707454"
---
# <a name="ihostmemorymanagervirtualprotect-method"></a><span data-ttu-id="0151e-103">IHostMemoryManager::VirtualProtect (Método)</span><span class="sxs-lookup"><span data-stu-id="0151e-103">IHostMemoryManager::VirtualProtect Method</span></span>

<span data-ttu-id="0151e-104">Actúa como un contenedor lógico para la función de Win32 correspondiente.</span><span class="sxs-lookup"><span data-stu-id="0151e-104">Serves as a logical wrapper for the corresponding Win32 function.</span></span> <span data-ttu-id="0151e-105">La implementación de Win32 de `VirtualProtect` cambia la protección en una región de páginas confirmadas en el espacio de direcciones virtuales del proceso de llamada.</span><span class="sxs-lookup"><span data-stu-id="0151e-105">The Win32 implementation of `VirtualProtect` changes the protection on a region of committed pages in the virtual address space of the calling process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0151e-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0151e-106">Syntax</span></span>  
  
```cpp  
HRESULT VirtualProtect (  
    [in]  void*   lpAddress,  
    [in]  SIZE_T  dwSize,  
    [in]  DWORD   flNewProtect,  
    [out] DWORD*  pflOldProtect  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0151e-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0151e-107">Parameters</span></span>  

 `lpAddress`  
 <span data-ttu-id="0151e-108">de Puntero a la dirección base de la memoria virtual cuyos atributos de protección se van a cambiar.</span><span class="sxs-lookup"><span data-stu-id="0151e-108">[in] A pointer to the base address of the virtual memory whose protection attributes are to be changed.</span></span>  
  
 `dwSize`  
 <span data-ttu-id="0151e-109">de Tamaño, en bytes, del área de páginas de memoria que se va a cambiar.</span><span class="sxs-lookup"><span data-stu-id="0151e-109">[in] The size, in bytes, of the region of memory pages to be changed.</span></span>  
  
 `flNewProtect`  
 <span data-ttu-id="0151e-110">de El tipo de protección de memoria que se va a aplicar.</span><span class="sxs-lookup"><span data-stu-id="0151e-110">[in] The type of memory protection to apply.</span></span>  
  
 `pflOldProtect`  
 <span data-ttu-id="0151e-111">enuncia Puntero al valor de protección de memoria anterior.</span><span class="sxs-lookup"><span data-stu-id="0151e-111">[out] A pointer to the previous memory protection value.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0151e-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0151e-112">Return Value</span></span>  
  
|<span data-ttu-id="0151e-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0151e-113">HRESULT</span></span>|<span data-ttu-id="0151e-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="0151e-114">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0151e-115">S_OK</span><span class="sxs-lookup"><span data-stu-id="0151e-115">S_OK</span></span>|<span data-ttu-id="0151e-116">`VirtualProtect` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="0151e-116">`VirtualProtect` returned successfully.</span></span>|  
|<span data-ttu-id="0151e-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="0151e-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="0151e-118">El Common Language Runtime (CLR) no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="0151e-118">The common language runtime (CLR) has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="0151e-119">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="0151e-119">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="0151e-120">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="0151e-120">The call timed out.</span></span>|  
|<span data-ttu-id="0151e-121">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="0151e-121">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="0151e-122">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="0151e-122">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="0151e-123">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="0151e-123">HOST_E_ABANDONED</span></span>|<span data-ttu-id="0151e-124">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="0151e-124">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="0151e-125">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="0151e-125">E_FAIL</span></span>|<span data-ttu-id="0151e-126">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="0151e-126">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="0151e-127">Cuando un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="0151e-127">When a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="0151e-128">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="0151e-128">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="0151e-129">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0151e-129">Remarks</span></span>  

 <span data-ttu-id="0151e-130">Esta implementación de `VirtualProtect` devuelve un valor HRESULT, mientras que la implementación de Win32 devuelve un valor distinto de cero para indicar que se ha realizado correctamente y un valor de cero para indicar el error.</span><span class="sxs-lookup"><span data-stu-id="0151e-130">This implementation of `VirtualProtect` returns an HRESULT value, while the Win32 implementation returns a non-zero value to indicate success, and a zero value to indicate failure.</span></span> <span data-ttu-id="0151e-131">Para obtener más información, vea la documentación de la plataforma Windows.</span><span class="sxs-lookup"><span data-stu-id="0151e-131">For more information, see the Windows Platform documentation.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0151e-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0151e-132">Requirements</span></span>  

 <span data-ttu-id="0151e-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0151e-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0151e-134">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="0151e-134">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="0151e-135">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0151e-135">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0151e-136">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0151e-136">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0151e-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="0151e-137">See also</span></span>

- [<span data-ttu-id="0151e-138">IHostMemoryManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0151e-138">IHostMemoryManager Interface</span></span>](ihostmemorymanager-interface.md)
