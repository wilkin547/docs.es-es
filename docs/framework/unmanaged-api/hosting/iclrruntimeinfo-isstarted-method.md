---
title: ICLRRuntimeInfo::IsStarted (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.IsStarted
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::IsStarted
helpviewer_keywords:
- IsStarted method [.NET Framework hosting]
- ICLRRuntimeInfo::IsStarted method [.NET Framework hosting]
ms.assetid: ef6f2662-323b-4534-aa82-6d1afb7b9309
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cb23a8e4237ff9b4b217458150c1f04956e439ec
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54526602"
---
# <a name="iclrruntimeinfoisstarted-method"></a><span data-ttu-id="758b0-102">ICLRRuntimeInfo::IsStarted (Método)</span><span class="sxs-lookup"><span data-stu-id="758b0-102">ICLRRuntimeInfo::IsStarted Method</span></span>
<span data-ttu-id="758b0-103">Indica si se ha iniciado el tiempo de ejecución (es decir, si la [ICLRRuntimeHost::](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) se ha llamado y se ha realizado correctamente).</span><span class="sxs-lookup"><span data-stu-id="758b0-103">Indicates whether the runtime has been started (that is, whether the [ICLRRuntimeHost::Start method](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) has been called and has succeeded).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="758b0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="758b0-104">Syntax</span></span>  
  
```  
HRESULT IsStarted(  
        [out] BOOL     *pbStarted,  
        [out] DWORD    *pdwStartupFlags);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="758b0-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="758b0-105">Parameters</span></span>  
 `pbStarted`  
 <span data-ttu-id="758b0-106">[out] `true` si este tiempo de ejecución está iniciado; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="758b0-106">[out] `true` if this runtime is started; otherwise, `false`.</span></span>  
  
 `pdwStartupFlags`  
 <span data-ttu-id="758b0-107">[out] Devuelve las marcas que se usaron para iniciar el tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="758b0-107">[out] Returns the flags that were used to start the runtime.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="758b0-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="758b0-108">Return Value</span></span>  
 <span data-ttu-id="758b0-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="758b0-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="758b0-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="758b0-110">HRESULT</span></span>|<span data-ttu-id="758b0-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="758b0-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="758b0-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="758b0-112">S_OK</span></span>|<span data-ttu-id="758b0-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="758b0-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="758b0-114">E_NOTIMPL</span><span class="sxs-lookup"><span data-stu-id="758b0-114">E_NOTIMPL</span></span>|<span data-ttu-id="758b0-115">La versión de common language runtime (CLR) es anterior a la versión de CLR en el [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="758b0-115">The common language runtime (CLR) version is earlier than the CLR version in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="758b0-116">Comentarios</span><span class="sxs-lookup"><span data-stu-id="758b0-116">Remarks</span></span>  
 <span data-ttu-id="758b0-117">Este método no funciona con las versiones CLR anteriores a la versión de CLR en el [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span><span class="sxs-lookup"><span data-stu-id="758b0-117">This method does not work with CLR versions earlier than the CLR version in the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)].</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="758b0-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="758b0-118">Requirements</span></span>  
 <span data-ttu-id="758b0-119">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="758b0-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="758b0-120">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="758b0-120">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="758b0-121">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="758b0-121">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="758b0-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="758b0-122">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="758b0-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="758b0-123">See also</span></span>
- [<span data-ttu-id="758b0-124">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="758b0-124">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="758b0-125">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="758b0-125">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="758b0-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="758b0-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
