---
title: ICorRuntimeHost::Stop (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Stop
helpviewer_keywords:
- Stop method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Stop method [.NET Framework hosting]
ms.assetid: 46a0d450-b516-4bef-8b71-8d3bf265cbed
topic_type:
- apiref
ms.openlocfilehash: 5fcf8bc861b2ef0b8ea9f5a5e46585564cc26615
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127702"
---
# <a name="icorruntimehoststop-method"></a><span data-ttu-id="04797-102">ICorRuntimeHost::Stop (Método)</span><span class="sxs-lookup"><span data-stu-id="04797-102">ICorRuntimeHost::Stop Method</span></span>
<span data-ttu-id="04797-103">Detiene la ejecución de código en tiempo de ejecución para el proceso actual.</span><span class="sxs-lookup"><span data-stu-id="04797-103">Stops the execution of code in the runtime for the current process.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04797-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04797-104">Syntax</span></span>  
  
```cpp  
HRESULT Stop ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="04797-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="04797-105">Return Value</span></span>  
  
|<span data-ttu-id="04797-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="04797-106">HRESULT</span></span>|<span data-ttu-id="04797-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="04797-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="04797-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="04797-108">S_OK</span></span>|<span data-ttu-id="04797-109">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="04797-109">The operation was successful.</span></span>|  
|<span data-ttu-id="04797-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="04797-110">S_FALSE</span></span>|<span data-ttu-id="04797-111">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="04797-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="04797-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="04797-112">E_FAIL</span></span>|<span data-ttu-id="04797-113">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="04797-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="04797-114">Si un método devuelve E_FAIL, el Common Language Runtime (CLR) ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="04797-114">If a method returns E_FAIL, the common language runtime (CLR) is no longer usable in the process.</span></span> <span data-ttu-id="04797-115">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="04797-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="04797-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="04797-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="04797-117">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="04797-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="04797-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04797-118">Remarks</span></span>  
 <span data-ttu-id="04797-119">Normalmente no es necesario llamar al método `Stop`, porque el código deja de ejecutarse cuando finaliza el proceso.</span><span class="sxs-lookup"><span data-stu-id="04797-119">It is typically unnecessary to call the `Stop` method, because the code stops executing when the process exits.</span></span>  
  
> [!NOTE]
> <span data-ttu-id="04797-120">Después de una llamada a `Stop`, CLR no se puede reinicializar en el mismo proceso.</span><span class="sxs-lookup"><span data-stu-id="04797-120">After a call to `Stop`, the CLR cannot be reinitialized into the same process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="04797-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04797-121">Requirements</span></span>  
 <span data-ttu-id="04797-122">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04797-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04797-123">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="04797-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04797-124">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="04797-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04797-125">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="04797-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04797-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="04797-126">See also</span></span>

- [<span data-ttu-id="04797-127">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="04797-127">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
