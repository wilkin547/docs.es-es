---
description: 'Más información acerca de: CLRCreateInstance (función)'
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
ms.openlocfilehash: 3b4dd9f07444f3e7ca68af3b85a7a053fc72b772
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799946"
---
# <a name="clrcreateinstance-function"></a><span data-ttu-id="23d48-103">CLRCreateInstance (Función)</span><span class="sxs-lookup"><span data-stu-id="23d48-103">CLRCreateInstance Function</span></span>

<span data-ttu-id="23d48-104">Proporciona una de las tres interfaces: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md)o [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="23d48-104">Provides one of three interfaces: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md), or [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="23d48-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="23d48-105">Syntax</span></span>  
  
```cpp  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="23d48-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="23d48-106">Parameters</span></span>  

 `clsid`  
 <span data-ttu-id="23d48-107">de Uno de los tres identificadores de clase: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy o CLSID_CLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="23d48-107">[in] One of three class identifiers: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, or CLSID_CLRDebugging.</span></span>  
  
 `riid`  
 <span data-ttu-id="23d48-108">de Uno de los tres identificadores de interfaz (IID): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy o IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="23d48-108">[in] One of three interface identifiers (IIDs): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, or IID_ICLRDebugging.</span></span>  
  
 `ppInterface`  
 <span data-ttu-id="23d48-109">enuncia Una de las tres interfaces: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md)o [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="23d48-109">[out] One of three interfaces: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md), or [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="23d48-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="23d48-110">Return Value</span></span>  

 <span data-ttu-id="23d48-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="23d48-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="23d48-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="23d48-112">HRESULT</span></span>|<span data-ttu-id="23d48-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="23d48-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="23d48-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="23d48-114">S_OK</span></span>|<span data-ttu-id="23d48-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="23d48-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="23d48-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="23d48-116">E_POINTER</span></span>|<span data-ttu-id="23d48-117">`ppInterface` es null.</span><span class="sxs-lookup"><span data-stu-id="23d48-117">`ppInterface` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="23d48-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="23d48-118">Remarks</span></span>  

 <span data-ttu-id="23d48-119">En la tabla siguiente se muestran las combinaciones admitidas para `clsid` y `riid` .</span><span class="sxs-lookup"><span data-stu-id="23d48-119">The following table shows the supported combinations for `clsid` and `riid`.</span></span>  
  
|`clsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="23d48-120">CLSID_CLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="23d48-120">CLSID_CLRMetaHost</span></span>|<span data-ttu-id="23d48-121">IID_ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="23d48-121">IID_ICLRMetaHost</span></span>|  
|<span data-ttu-id="23d48-122">CLSID_CLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="23d48-122">CLSID_CLRMetaHostPolicy</span></span>|<span data-ttu-id="23d48-123">IID_ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="23d48-123">IID_ICLRMetaHostPolicy</span></span>|  
|<span data-ttu-id="23d48-124">CLSID_CLRDebugging</span><span class="sxs-lookup"><span data-stu-id="23d48-124">CLSID_CLRDebugging</span></span>|<span data-ttu-id="23d48-125">IID_ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="23d48-125">IID_ICLRDebugging</span></span>|  
  
 <span data-ttu-id="23d48-126">En el código siguiente se muestra cómo usar `CLRCreateInstance` para obtener las tres interfaces:</span><span class="sxs-lookup"><span data-stu-id="23d48-126">The following code shows how to use `CLRCreateInstance` to get all three interfaces:</span></span>  
  
```cpp  
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
  
## <a name="requirements"></a><span data-ttu-id="23d48-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="23d48-127">Requirements</span></span>  

 <span data-ttu-id="23d48-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="23d48-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23d48-129">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="23d48-129">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="23d48-130">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="23d48-130">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="23d48-131">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23d48-131">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23d48-132">Vea también</span><span class="sxs-lookup"><span data-stu-id="23d48-132">See also</span></span>

- [<span data-ttu-id="23d48-133">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="23d48-133">Hosting</span></span>](index.md)
