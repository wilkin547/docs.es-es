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
ms.openlocfilehash: ac81aeadce651a04e2cabc8a6740fe86825edcc3
ms.sourcegitcommit: 44af69720863bd09bd7a4509bf1ec119466ba6e8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/02/2021
ms.locfileid: "106231354"
---
# <a name="clrcreateinstance-function"></a><span data-ttu-id="f766a-103">CLRCreateInstance (Función)</span><span class="sxs-lookup"><span data-stu-id="f766a-103">CLRCreateInstance Function</span></span>

<span data-ttu-id="f766a-104">Proporciona una de las tres interfaces: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md)o [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f766a-104">Provides one of three interfaces: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md), or [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f766a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f766a-105">Syntax</span></span>  
  
```cpp  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f766a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f766a-106">Parameters</span></span>  

 `clsid`  
 <span data-ttu-id="f766a-107">de Uno de los tres identificadores de clase: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy o CLSID_CLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="f766a-107">[in] One of three class identifiers: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, or CLSID_CLRDebugging.</span></span>  
  
 `riid`  
 <span data-ttu-id="f766a-108">de Uno de los tres identificadores de interfaz (IID): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy o IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="f766a-108">[in] One of three interface identifiers (IIDs): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, or IID_ICLRDebugging.</span></span>  
  
 `ppInterface`  
 <span data-ttu-id="f766a-109">enuncia Una de las tres interfaces: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md)o [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="f766a-109">[out] One of three interfaces: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md), or [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f766a-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f766a-110">Return Value</span></span>  

 <span data-ttu-id="f766a-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="f766a-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="f766a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f766a-112">HRESULT</span></span>|<span data-ttu-id="f766a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="f766a-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="f766a-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="f766a-114">S_OK</span></span>|<span data-ttu-id="f766a-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="f766a-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="f766a-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="f766a-116">E_POINTER</span></span>|<span data-ttu-id="f766a-117">`ppInterface` es null.</span><span class="sxs-lookup"><span data-stu-id="f766a-117">`ppInterface` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f766a-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="f766a-118">Remarks</span></span>  

 <span data-ttu-id="f766a-119">En la tabla siguiente se muestran las combinaciones admitidas para `clsid` y `riid` .</span><span class="sxs-lookup"><span data-stu-id="f766a-119">The following table shows the supported combinations for `clsid` and `riid`.</span></span>  
  
|`clsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="f766a-120">CLSID_CLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="f766a-120">CLSID_CLRMetaHost</span></span>|<span data-ttu-id="f766a-121">IID_ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="f766a-121">IID_ICLRMetaHost</span></span>|  
|<span data-ttu-id="f766a-122">CLSID_CLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="f766a-122">CLSID_CLRMetaHostPolicy</span></span>|<span data-ttu-id="f766a-123">IID_ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="f766a-123">IID_ICLRMetaHostPolicy</span></span>|  
|<span data-ttu-id="f766a-124">CLSID_CLRDebugging</span><span class="sxs-lookup"><span data-stu-id="f766a-124">CLSID_CLRDebugging</span></span>|<span data-ttu-id="f766a-125">IID_ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="f766a-125">IID_ICLRDebugging</span></span>|  
  
 <span data-ttu-id="f766a-126">En el código siguiente se muestra cómo usar `CLRCreateInstance` para obtener las tres interfaces:</span><span class="sxs-lookup"><span data-stu-id="f766a-126">The following code shows how to use `CLRCreateInstance` to get all three interfaces:</span></span>  
  
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

<span data-ttu-id="f766a-127">La `CreateInterface` función tiene un alias `CLRCreateInstance` .</span><span class="sxs-lookup"><span data-stu-id="f766a-127">The `CreateInterface` function is aliased to `CLRCreateInstance`.</span></span>  <span data-ttu-id="f766a-128">`CLRCreateInstance` `CreateInterface` Las funciones y se pueden usar indistintamente.</span><span class="sxs-lookup"><span data-stu-id="f766a-128">Both `CLRCreateInstance` and `CreateInterface` functions can be used interchangeably.</span></span> <span data-ttu-id="f766a-129">Por ejemplo:</span><span class="sxs-lookup"><span data-stu-id="f766a-129">For example:</span></span>

```cpp
HMODULE hModule = LoadLibrary(L"mscoree.dll");
CreateInterfaceFnPtr createInterface = (CreateInterfaceFnPtr)GetProcAddress(hModule, "CreateInterface");
HRESULT hr;
hr = createInterface(CLSID_CLRMetaHost, IID_ICLRMetaHost, (LPVOID*)&pMetaHost);
hr = createInterface (CLSID_CLRMetaHostPolicy, IID_ICLRMetaHostPolicy,  (LPVOID*)&pMetaHostPolicy);  
hr = createInterface (CLSID_CLRDebugging, IID_ICLRDebugging,  (LPVOID*)&pCLRDebugging);
```
  
## <a name="requirements"></a><span data-ttu-id="f766a-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f766a-130">Requirements</span></span>  

 <span data-ttu-id="f766a-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f766a-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f766a-132">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="f766a-132">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="f766a-133">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f766a-133">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f766a-134">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f766a-134">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f766a-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f766a-135">See also</span></span>

- [<span data-ttu-id="f766a-136">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="f766a-136">Hosting</span></span>](index.md)
