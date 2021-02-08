---
description: 'Más información acerca de: ICorRuntimeHost:: Start (método)'
title: ICorRuntimeHost::Start (Método)
ms.date: 03/30/2017
api_name:
- ICorRuntimeHost.Start
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICorRuntimeHost::Start
helpviewer_keywords:
- Start method, ICorRuntimeHost interface [.NET Framework hosting]
- ICorRuntimeHost::Start method [.NET Framework hosting]
ms.assetid: c66f3ac5-6489-484a-9bed-c31b711cee01
topic_type:
- apiref
ms.openlocfilehash: d07c0144c7192bc2f57927c294ea472cd6b47f9f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789611"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="a3b2d-103">ICorRuntimeHost::Start (Método)</span><span class="sxs-lookup"><span data-stu-id="a3b2d-103">ICorRuntimeHost::Start Method</span></span>

<span data-ttu-id="a3b2d-104">Inicia el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="a3b2d-104">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a3b2d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a3b2d-105">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="a3b2d-106">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a3b2d-106">Return Value</span></span>  
  
|<span data-ttu-id="a3b2d-107">HRESULT</span><span class="sxs-lookup"><span data-stu-id="a3b2d-107">HRESULT</span></span>|<span data-ttu-id="a3b2d-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="a3b2d-108">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="a3b2d-109">S_OK</span><span class="sxs-lookup"><span data-stu-id="a3b2d-109">S_OK</span></span>|<span data-ttu-id="a3b2d-110">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="a3b2d-110">The operation was successful.</span></span>|  
|<span data-ttu-id="a3b2d-111">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="a3b2d-111">S_FALSE</span></span>|<span data-ttu-id="a3b2d-112">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="a3b2d-112">The operation failed to complete.</span></span>|  
|<span data-ttu-id="a3b2d-113">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="a3b2d-113">E_FAIL</span></span>|<span data-ttu-id="a3b2d-114">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="a3b2d-114">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="a3b2d-115">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="a3b2d-115">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="a3b2d-116">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="a3b2d-116">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="a3b2d-117">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="a3b2d-117">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="a3b2d-118">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="a3b2d-118">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a3b2d-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="a3b2d-119">Remarks</span></span>  

 <span data-ttu-id="a3b2d-120">Normalmente no es necesario llamar al `Start` método, ya que CLR se inicia automáticamente tras la primera solicitud para ejecutar el código administrado.</span><span class="sxs-lookup"><span data-stu-id="a3b2d-120">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a3b2d-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a3b2d-121">Requirements</span></span>  

 <span data-ttu-id="a3b2d-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a3b2d-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a3b2d-123">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="a3b2d-123">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a3b2d-124">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a3b2d-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a3b2d-125">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="a3b2d-125">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a3b2d-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="a3b2d-126">See also</span></span>

- [<span data-ttu-id="a3b2d-127">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a3b2d-127">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
