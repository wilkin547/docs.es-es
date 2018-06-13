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
ms.openlocfilehash: 96e8d80e2dff88aa5a589f864278b4a4e9cc76ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33437019"
---
# <a name="icorruntimehoststart-method"></a><span data-ttu-id="bbc08-102">ICorRuntimeHost::Start (Método)</span><span class="sxs-lookup"><span data-stu-id="bbc08-102">ICorRuntimeHost::Start Method</span></span>
<span data-ttu-id="bbc08-103">Inicia common language runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="bbc08-103">Starts the common language runtime (CLR).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bbc08-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="bbc08-104">Syntax</span></span>  
  
```  
HRESULT Start ();  
```  
  
## <a name="return-value"></a><span data-ttu-id="bbc08-105">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="bbc08-105">Return Value</span></span>  
  
|<span data-ttu-id="bbc08-106">HRESULT</span><span class="sxs-lookup"><span data-stu-id="bbc08-106">HRESULT</span></span>|<span data-ttu-id="bbc08-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="bbc08-107">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="bbc08-108">S_OK</span><span class="sxs-lookup"><span data-stu-id="bbc08-108">S_OK</span></span>|<span data-ttu-id="bbc08-109">La operación fue correcta.</span><span class="sxs-lookup"><span data-stu-id="bbc08-109">The operation was successful.</span></span>|  
|<span data-ttu-id="bbc08-110">S_FALSE</span><span class="sxs-lookup"><span data-stu-id="bbc08-110">S_FALSE</span></span>|<span data-ttu-id="bbc08-111">No se pudo completar la operación.</span><span class="sxs-lookup"><span data-stu-id="bbc08-111">The operation failed to complete.</span></span>|  
|<span data-ttu-id="bbc08-112">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="bbc08-112">E_FAIL</span></span>|<span data-ttu-id="bbc08-113">Se ha producido un error catastrófico desconocido.</span><span class="sxs-lookup"><span data-stu-id="bbc08-113">An unknown, catastrophic failure occurred.</span></span> <span data-ttu-id="bbc08-114">Si el método devuelve E_FAIL, CLR ya no es utilizable en el proceso.</span><span class="sxs-lookup"><span data-stu-id="bbc08-114">If a method returns E_FAIL, the CLR is no longer usable in the process.</span></span> <span data-ttu-id="bbc08-115">Las llamadas subsiguientes a cualquier API de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="bbc08-115">Subsequent calls to any hosting APIs return HOST_E_CLRNOTAVAILABLE.</span></span>|  
|<span data-ttu-id="bbc08-116">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="bbc08-116">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="bbc08-117">El CLR no se han cargado en un proceso o el CLR está en un estado en el que no se puede ejecutar código administrado o procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="bbc08-117">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="bbc08-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="bbc08-118">Remarks</span></span>  
 <span data-ttu-id="bbc08-119">Normalmente no es necesario llamar a la `Start` método, ya que el CLR se inicia automáticamente tras la primera solicitud para ejecutar código administrado.</span><span class="sxs-lookup"><span data-stu-id="bbc08-119">It is typically not necessary to call the `Start` method, because the CLR starts automatically upon the first request to run managed code.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="bbc08-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="bbc08-120">Requirements</span></span>  
 <span data-ttu-id="bbc08-121">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="bbc08-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="bbc08-122">**Encabezado:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="bbc08-122">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="bbc08-123">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="bbc08-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="bbc08-124">**Versiones de .NET framework:** 1.0, 1.1</span><span class="sxs-lookup"><span data-stu-id="bbc08-124">**.NET Framework Versions:** 1.0, 1.1</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bbc08-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="bbc08-125">See Also</span></span>  
 [<span data-ttu-id="bbc08-126">ICorRuntimeHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="bbc08-126">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)
