---
title: CLRCreateInstance (Función)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4ab16d78b210c2824bf6172f80d1b15e3533a05b
ms.sourcegitcommit: 89c93d05c2281b4c834f48f6c8df1047e1410980
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2018
ms.locfileid: "34172141"
---
# <a name="clrcreateinstance-function"></a><span data-ttu-id="676f4-102">CLRCreateInstance (Función)</span><span class="sxs-lookup"><span data-stu-id="676f4-102">CLRCreateInstance Function</span></span>
<span data-ttu-id="676f4-103">Proporciona una de tres interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), o [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="676f4-103">Provides one of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="676f4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="676f4-104">Syntax</span></span>  
  
```  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="676f4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="676f4-105">Parameters</span></span>  
 `clsid`  
 <span data-ttu-id="676f4-106">[in] Uno de tres identificadores de clase: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy o CLSID_CLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="676f4-106">[in] One of three class identifiers: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, or CLSID_CLRDebugging.</span></span>  
  
 `riid`  
 <span data-ttu-id="676f4-107">[in] Uno de tres identificadores de interfaz (IID): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy o IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="676f4-107">[in] One of three interface identifiers (IIDs): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, or IID_ICLRDebugging.</span></span>  
  
 `ppInterface`  
 <span data-ttu-id="676f4-108">[out] Uno de tres interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), o [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="676f4-108">[out] One of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="676f4-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="676f4-109">Return Value</span></span>  
 <span data-ttu-id="676f4-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="676f4-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="676f4-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="676f4-111">HRESULT</span></span>|<span data-ttu-id="676f4-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="676f4-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="676f4-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="676f4-113">S_OK</span></span>|<span data-ttu-id="676f4-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="676f4-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="676f4-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="676f4-115">E_POINTER</span></span>|<span data-ttu-id="676f4-116">`ppInterface` es null.</span><span class="sxs-lookup"><span data-stu-id="676f4-116">`ppInterface` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="676f4-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="676f4-117">Remarks</span></span>  
 <span data-ttu-id="676f4-118">La tabla siguiente muestran las combinaciones admitidas para `clsid` y `riid`.</span><span class="sxs-lookup"><span data-stu-id="676f4-118">The following table shows the supported combinations for `clsid` and `riid`.</span></span>  
  
|`clsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="676f4-119">CLSID_CLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="676f4-119">CLSID_CLRMetaHost</span></span>|<span data-ttu-id="676f4-120">IID_ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="676f4-120">IID_ICLRMetaHost</span></span>|  
|<span data-ttu-id="676f4-121">CLSID_CLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="676f4-121">CLSID_CLRMetaHostPolicy</span></span>|<span data-ttu-id="676f4-122">IID_ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="676f4-122">IID_ICLRMetaHostPolicy</span></span>|  
|<span data-ttu-id="676f4-123">CLSID_CLRDebugging</span><span class="sxs-lookup"><span data-stu-id="676f4-123">CLSID_CLRDebugging</span></span>|<span data-ttu-id="676f4-124">IID_ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="676f4-124">IID_ICLRDebugging</span></span>|  
  
 <span data-ttu-id="676f4-125">El código siguiente muestra cómo utilizar `CLRCreateInstance` para obtener las tres interfaces:</span><span class="sxs-lookup"><span data-stu-id="676f4-125">The following code shows how to use `CLRCreateInstance` to get all three interfaces:</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="676f4-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="676f4-126">Requirements</span></span>  
 <span data-ttu-id="676f4-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="676f4-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="676f4-128">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="676f4-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="676f4-129">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="676f4-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="676f4-130">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="676f4-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="676f4-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="676f4-131">See Also</span></span>  
 [<span data-ttu-id="676f4-132">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="676f4-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
