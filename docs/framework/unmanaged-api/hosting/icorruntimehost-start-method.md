---
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
ms.openlocfilehash: bc647ad025b5e22187b476383ed0128761cb632f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721041"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="76323-102">ICorRuntimeHost::Start (Método)</span><span class="sxs-lookup"><span data-stu-id="76323-102">ICorRuntimeHost::Start Method</span></span>

<span data-ttu-id="76323-103">Inicia el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="76323-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76323-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76323-104">Syntax</span></span>  
  
```cpp  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="76323-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="76323-105">Return Value</span></span>  
  
|<span data-ttu-id="76323-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="76323-106">HRESULT</span></span>|<span data-ttu-id="76323-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="76323-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="76323-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="76323-108">S_OK</span></span>|<span data-ttu-id="76323-109">La operación se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="76323-109">The operation was successful.</span></span>|  
|<span data-ttu-id="76323-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="76323-110">S_FALSE</span></span>|<span data-ttu-id="76323-111">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="76323-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="76323-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="76323-112">E_FAIL</span></span>|<span data-ttu-id="76323-113">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="76323-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="76323-114">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="76323-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="76323-115">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="76323-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="76323-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="76323-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="76323-117">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="76323-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76323-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="76323-118">Remarks</span></span>  

 <span data-ttu-id="76323-119">Normalmente no es necesario llamar al `Start` método, ya que CLR se inicia automáticamente tras la primera solicitud para ejecutar el código administrado.</span><span class="sxs-lookup"><span data-stu-id="76323-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76323-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76323-120">Requirements</span></span>  

 <span data-ttu-id="76323-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76323-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76323-122">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="76323-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="76323-123">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="76323-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76323-124">**.NET Framework versiones:** 1,0, 1,1</span><span class="sxs-lookup"><span data-stu-id="76323-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76323-125">Consulte también</span><span class="sxs-lookup"><span data-stu-id="76323-125">See also</span></span>

- [<span data-ttu-id="76323-126">ICorRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="76323-126">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)
