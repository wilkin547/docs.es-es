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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5e6521f8013bf92f073ab4b6808871c95ac2802b
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61700116"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="e33fc-102">ICorRuntimeHost::Start (Método)</span><span class="sxs-lookup"><span data-stu-id="e33fc-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="e33fc-103">Se inicia common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="e33fc-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e33fc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e33fc-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="e33fc-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e33fc-105">Return Value</span></span>  
  
|<span data-ttu-id="e33fc-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e33fc-106">HRESULT</span></span>|<span data-ttu-id="e33fc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e33fc-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e33fc-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="e33fc-108">S_OK</span></span>|<span data-ttu-id="e33fc-109">La operación fue correcta.</span><span class="sxs-lookup"><span data-stu-id="e33fc-109">The operation was successful.</span></span>|  
|<span data-ttu-id="e33fc-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="e33fc-110">S_FALSE</span></span>|<span data-ttu-id="e33fc-111">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="e33fc-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="e33fc-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="e33fc-112">E_FAIL</span></span>|<span data-ttu-id="e33fc-113">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="e33fc-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="e33fc-114">Si el método devuelve E_FAIL, CLR ya no es utilizable en el proceso.</span><span class="sxs-lookup"><span data-stu-id="e33fc-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="e33fc-115">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="e33fc-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="e33fc-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="e33fc-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="e33fc-117">El CLR no se ha cargado en un proceso o el CLR se encuentra en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="e33fc-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e33fc-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e33fc-118">Remarks</span></span>  
 <span data-ttu-id="e33fc-119">Normalmente no es necesario llamar a la `Start` método, ya que el CLR se inicia automáticamente tras la primera solicitud para ejecutar código administrado.</span><span class="sxs-lookup"><span data-stu-id="e33fc-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e33fc-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e33fc-120">Requirements</span></span>  
 <span data-ttu-id="e33fc-121">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e33fc-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e33fc-122">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="e33fc-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="e33fc-123">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e33fc-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e33fc-124">**Versiones de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="e33fc-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e33fc-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="e33fc-125">See also</span></span>

- [<span data-ttu-id="e33fc-126">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="e33fc-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
