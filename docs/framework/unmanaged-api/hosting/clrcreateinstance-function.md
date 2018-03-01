---
title: "CLRCreateInstance (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CLRCreateInstance
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- CLRCreateInstance
helpviewer_keywords:
- CLRCreateInstance function [.NET Framework hosting]
ms.assetid: 5de13327-96c6-4697-a89e-b8bf40717855
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 4d95815dd0b2a1cdbddcb28a2e176bc12d3270ed
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="clrcreateinstance-function"></a><span data-ttu-id="6c009-102">CLRCreateInstance (Función)</span><span class="sxs-lookup"><span data-stu-id="6c009-102">CLRCreateInstance Function</span></span>
<span data-ttu-id="6c009-103">Proporciona una de tres interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), o [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6c009-103">Provides one of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c009-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6c009-104">Syntax</span></span>  
  
```  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="6c009-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6c009-105">Parameters</span></span>  
 `clsid`  
 <span data-ttu-id="6c009-106">[in] Uno de tres identificadores de clase: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy o CLSID_CLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="6c009-106">[in] One of three class identifiers: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, or CLSID_CLRDebugging.</span></span>  
  
 `riid`  
 <span data-ttu-id="6c009-107">[in] Uno de tres identificadores de interfaz (IID): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy o IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="6c009-107">[in] One of three interface identifiers (IIDs): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, or IID_ICLRDebugging.</span></span>  
  
 `ppInterface`  
 <span data-ttu-id="6c009-108">[out] Uno de tres interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), o [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="6c009-108">[out] One of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6c009-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6c009-109">Return Value</span></span>  
 <span data-ttu-id="6c009-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="6c009-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="6c009-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6c009-111">HRESULT</span></span>|<span data-ttu-id="6c009-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="6c009-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="6c009-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="6c009-113">S_OK</span></span>|<span data-ttu-id="6c009-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="6c009-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="6c009-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="6c009-115">E_POINTER</span></span>|<span data-ttu-id="6c009-116">`ppInterface` es null.</span><span class="sxs-lookup"><span data-stu-id="6c009-116">`ppInterface` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6c009-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6c009-117">Remarks</span></span>  
 <span data-ttu-id="6c009-118">La tabla siguiente muestran las combinaciones admitidas para `clsid` y `riid`.</span><span class="sxs-lookup"><span data-stu-id="6c009-118">The following table shows the supported combinations for `clsid` and `riid`.</span></span>  
  
|`rclsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="6c009-119">CLSID_CLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="6c009-119">CLSID_CLRMetaHost</span></span>|<span data-ttu-id="6c009-120">IID_ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="6c009-120">IID_ICLRMetaHost</span></span>|  
|<span data-ttu-id="6c009-121">CLSID_CLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="6c009-121">CLSID_CLRMetaHostPolicy</span></span>|<span data-ttu-id="6c009-122">IID_ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="6c009-122">IID_ICLRMetaHostPolicy</span></span>|  
|<span data-ttu-id="6c009-123">CLSID_CLRDebugging</span><span class="sxs-lookup"><span data-stu-id="6c009-123">CLSID_CLRDebugging</span></span>|<span data-ttu-id="6c009-124">IID_ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="6c009-124">IID_ICLRDebugging</span></span>|  
  
 <span data-ttu-id="6c009-125">El código siguiente muestra cómo utilizar `CLRCreateInstance` para obtener las tres interfaces:</span><span class="sxs-lookup"><span data-stu-id="6c009-125">The following code shows how to use `CLRCreateInstance` to get all three interfaces:</span></span>  
  
```  
#include <metahost.h>  
#pragma comment(lib, "mscoree.lib")  
  
ICLRMetaHost       *pMetaHost       = NULL;  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
ICLRDebugging      *pCLRDebugging   = NULL;  
HRESULT hr;  
hr = CLRCreateInstance(CLSID_CLRMetaHost, IID_ICLRMetaHost,  
                    (LPVOID*)&pMetaHost);  
hr = CLRCreateInstance (CLSID_CLRMetaHostPolicy, IID_ICLRMetaHostPolicy,  
                    (LPVOID*)&pMetaHostPolicy);  
hr = CLRCreateInstance (CLSID_CLRDebugging, IID_ICLRDebugging,  
                    (LPVOID*)&pCLRDebugging);  
```  
  
## <a name="requirements"></a><span data-ttu-id="6c009-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6c009-126">Requirements</span></span>  
 <span data-ttu-id="6c009-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6c009-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c009-128">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="6c009-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="6c009-129">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6c009-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6c009-130">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c009-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c009-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="6c009-131">See Also</span></span>  
 [<span data-ttu-id="6c009-132">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="6c009-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
