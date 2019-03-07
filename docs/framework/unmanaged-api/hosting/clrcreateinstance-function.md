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
ms.openlocfilehash: a9b4e9149fa50a951f2a56c83412e42fe86b9563
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57501206"
---
# <a name="clrcreateinstance-function"></a><span data-ttu-id="e16fb-102">CLRCreateInstance (Función)</span><span class="sxs-lookup"><span data-stu-id="e16fb-102">CLRCreateInstance Function</span></span>
<span data-ttu-id="e16fb-103">Proporciona una de tres interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), o [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e16fb-103">Provides one of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e16fb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e16fb-104">Syntax</span></span>  
  
```  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e16fb-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e16fb-105">Parameters</span></span>  
 `clsid`  
 <span data-ttu-id="e16fb-106">[in] Uno de tres identificadores de clase: Argumentos CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy o CLSID_CLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="e16fb-106">[in] One of three class identifiers: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, or CLSID_CLRDebugging.</span></span>  
  
 `riid`  
 <span data-ttu-id="e16fb-107">[in] Uno de tres identificadores de interfaz (IID): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy o IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="e16fb-107">[in] One of three interface identifiers (IIDs): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, or IID_ICLRDebugging.</span></span>  
  
 `ppInterface`  
 <span data-ttu-id="e16fb-108">[out] Uno de tres interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), o [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="e16fb-108">[out] One of three interfaces: [ICLRMetaHost](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md), [ICLRMetaHostPolicy](../../../../docs/framework/unmanaged-api/hosting/iclrmetahostpolicy-interface.md), or [ICLRDebugging](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="e16fb-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e16fb-109">Return Value</span></span>  
 <span data-ttu-id="e16fb-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="e16fb-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="e16fb-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="e16fb-111">HRESULT</span></span>|<span data-ttu-id="e16fb-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="e16fb-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="e16fb-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="e16fb-113">S_OK</span></span>|<span data-ttu-id="e16fb-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e16fb-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="e16fb-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="e16fb-115">E_POINTER</span></span>|<span data-ttu-id="e16fb-116">`ppInterface` es null.</span><span class="sxs-lookup"><span data-stu-id="e16fb-116">`ppInterface` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e16fb-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e16fb-117">Remarks</span></span>  
 <span data-ttu-id="e16fb-118">La siguiente tabla muestra las combinaciones admitidas de `clsid` y `riid`.</span><span class="sxs-lookup"><span data-stu-id="e16fb-118">The following table shows the supported combinations for `clsid` and `riid`.</span></span>  
  
|`clsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="e16fb-119">CLSID_CLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="e16fb-119">CLSID_CLRMetaHost</span></span>|<span data-ttu-id="e16fb-120">IID_ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="e16fb-120">IID_ICLRMetaHost</span></span>|  
|<span data-ttu-id="e16fb-121">CLSID_CLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="e16fb-121">CLSID_CLRMetaHostPolicy</span></span>|<span data-ttu-id="e16fb-122">IID_ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="e16fb-122">IID_ICLRMetaHostPolicy</span></span>|  
|<span data-ttu-id="e16fb-123">CLSID_CLRDebugging</span><span class="sxs-lookup"><span data-stu-id="e16fb-123">CLSID_CLRDebugging</span></span>|<span data-ttu-id="e16fb-124">IID_ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="e16fb-124">IID_ICLRDebugging</span></span>|  
  
 <span data-ttu-id="e16fb-125">El código siguiente muestra cómo usar `CLRCreateInstance` para obtener las tres interfaces:</span><span class="sxs-lookup"><span data-stu-id="e16fb-125">The following code shows how to use `CLRCreateInstance` to get all three interfaces:</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="e16fb-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e16fb-126">Requirements</span></span>  
 <span data-ttu-id="e16fb-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e16fb-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e16fb-128">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="e16fb-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="e16fb-129">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e16fb-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="e16fb-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e16fb-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e16fb-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="e16fb-131">See also</span></span>
- [<span data-ttu-id="e16fb-132">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="e16fb-132">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
