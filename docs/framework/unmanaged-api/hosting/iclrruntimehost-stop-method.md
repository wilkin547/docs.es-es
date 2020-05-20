---
title: ICLRRuntimeHost::Stop (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeHost.Stop
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeHost::Stop
helpviewer_keywords:
- ICLRRuntimeHost::Stop method [.NET Framework hosting]
- Stop method, ICLRRuntimeHost interface [.NET Framework hosting]
ms.assetid: b8fd7daf-8f8d-4ad7-92ae-019db244cec1
topic_type:
- apiref
ms.openlocfilehash: 55cd444ffedc92ba74239421ae548ffd930e6ab7
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703928"
---
# <a name="iclrruntimehoststop-method"></a><span data-ttu-id="37ac2-102">ICLRRuntimeHost::Stop (Método)</span><span class="sxs-lookup"><span data-stu-id="37ac2-102">ICLRRuntimeHost::Stop Method</span></span>
<span data-ttu-id="37ac2-103">Detiene la ejecución de código por el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="37ac2-103">Stops the execution of code by the common language runtime (CLR).</span></span>  
  
> [!IMPORTANT]
> <span data-ttu-id="37ac2-104">Este método no libera los recursos en el host, descarga los dominios de aplicación ni destruye los subprocesos.</span><span class="sxs-lookup"><span data-stu-id="37ac2-104">This method does not release resources to the host, unload application domains, or destroy threads.</span></span> <span data-ttu-id="37ac2-105">Debe finalizar el proceso para liberar estos recursos.</span><span class="sxs-lookup"><span data-stu-id="37ac2-105">You must terminate the process to release these resources.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="37ac2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="37ac2-106">Syntax</span></span>  
  
```cpp  
HRESULT Stop();  
```  
  
## <a name="return-value"></a><span data-ttu-id="37ac2-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="37ac2-107">Return Value</span></span>  
  
|<span data-ttu-id="37ac2-108">HRESULT</span><span class="sxs-lookup"><span data-stu-id="37ac2-108">HRESULT</span></span>|<span data-ttu-id="37ac2-109">Descripción</span><span class="sxs-lookup"><span data-stu-id="37ac2-109">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="37ac2-110">S_OK</span><span class="sxs-lookup"><span data-stu-id="37ac2-110">S_OK</span></span>|<span data-ttu-id="37ac2-111">`Stop`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="37ac2-111">`Stop` returned successfully.</span></span>|  
|<span data-ttu-id="37ac2-112">HOST_E_CLRNOTAVAILABLE</span><span class="sxs-lookup"><span data-stu-id="37ac2-112">HOST_E_CLRNOTAVAILABLE</span></span>|<span data-ttu-id="37ac2-113">CLR no se ha cargado en un proceso o CLR está en un estado en el que no puede ejecutar código administrado ni procesar la llamada correctamente.</span><span class="sxs-lookup"><span data-stu-id="37ac2-113">The CLR has not been loaded into a process, or the CLR is in a state in which it cannot run managed code or process the call successfully.</span></span>|  
|<span data-ttu-id="37ac2-114">HOST_E_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="37ac2-114">HOST_E_TIMEOUT</span></span>|<span data-ttu-id="37ac2-115">Se agotó el tiempo de espera de la llamada.</span><span class="sxs-lookup"><span data-stu-id="37ac2-115">The call timed out.</span></span>|  
|<span data-ttu-id="37ac2-116">HOST_E_NOT_OWNER</span><span class="sxs-lookup"><span data-stu-id="37ac2-116">HOST_E_NOT_OWNER</span></span>|<span data-ttu-id="37ac2-117">El autor de la llamada no posee el bloqueo.</span><span class="sxs-lookup"><span data-stu-id="37ac2-117">The caller does not own the lock.</span></span>|  
|<span data-ttu-id="37ac2-118">HOST_E_ABANDONED</span><span class="sxs-lookup"><span data-stu-id="37ac2-118">HOST_E_ABANDONED</span></span>|<span data-ttu-id="37ac2-119">Se canceló un evento mientras un subproceso o fibra bloqueados estaba esperando en él.</span><span class="sxs-lookup"><span data-stu-id="37ac2-119">An event was canceled while a blocked thread or fiber was waiting on it.</span></span>|  
|<span data-ttu-id="37ac2-120">E_FAIL</span><span class="sxs-lookup"><span data-stu-id="37ac2-120">E_FAIL</span></span>|<span data-ttu-id="37ac2-121">Se produjo un error grave desconocido.</span><span class="sxs-lookup"><span data-stu-id="37ac2-121">An unknown catastrophic failure occurred.</span></span> <span data-ttu-id="37ac2-122">Si un método devuelve E_FAIL, CLR ya no se puede usar en el proceso.</span><span class="sxs-lookup"><span data-stu-id="37ac2-122">If a method returns E_FAIL, the CLR is no longer usable within the process.</span></span> <span data-ttu-id="37ac2-123">Las llamadas subsiguientes a métodos de hospedaje devuelven HOST_E_CLRNOTAVAILABLE.</span><span class="sxs-lookup"><span data-stu-id="37ac2-123">Subsequent calls to hosting methods return HOST_E_CLRNOTAVAILABLE.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="37ac2-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="37ac2-124">Requirements</span></span>  
 <span data-ttu-id="37ac2-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="37ac2-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="37ac2-126">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="37ac2-126">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="37ac2-127">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="37ac2-127">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="37ac2-128">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="37ac2-128">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="37ac2-129">Consulta también</span><span class="sxs-lookup"><span data-stu-id="37ac2-129">See also</span></span>

- [<span data-ttu-id="37ac2-130">ICLRRuntimeHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="37ac2-130">ICLRRuntimeHost Interface</span></span>](iclrruntimehost-interface.md)
