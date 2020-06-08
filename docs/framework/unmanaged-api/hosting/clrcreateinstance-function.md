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
ms.openlocfilehash: 4aeacc718632c133550ed8de6649716c5d8b7423
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504464"
---
# <a name="clrcreateinstance-function"></a><span data-ttu-id="47b53-102">CLRCreateInstance (Función)</span><span class="sxs-lookup"><span data-stu-id="47b53-102">CLRCreateInstance Function</span></span>
<span data-ttu-id="47b53-103">Proporciona una de las tres interfaces: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md)o [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="47b53-103">Provides one of three interfaces: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md), or [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="47b53-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47b53-104">Syntax</span></span>  
  
```cpp  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="47b53-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47b53-105">Parameters</span></span>  
 `clsid`  
 <span data-ttu-id="47b53-106">de Uno de los tres identificadores de clase: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy o CLSID_CLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="47b53-106">[in] One of three class identifiers: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy, or CLSID_CLRDebugging.</span></span>  
  
 `riid`  
 <span data-ttu-id="47b53-107">de Uno de los tres identificadores de interfaz (IID): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy o IID_ICLRDebugging.</span><span class="sxs-lookup"><span data-stu-id="47b53-107">[in] One of three interface identifiers (IIDs): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy, or IID_ICLRDebugging.</span></span>  
  
 `ppInterface`  
 <span data-ttu-id="47b53-108">enuncia Una de las tres interfaces: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md)o [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span><span class="sxs-lookup"><span data-stu-id="47b53-108">[out] One of three interfaces: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md), or [ICLRDebugging](../debugging/iclrdebugging-interface.md).</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="47b53-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="47b53-109">Return Value</span></span>  
 <span data-ttu-id="47b53-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="47b53-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="47b53-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="47b53-111">HRESULT</span></span>|<span data-ttu-id="47b53-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="47b53-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="47b53-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="47b53-113">S_OK</span></span>|<span data-ttu-id="47b53-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="47b53-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="47b53-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="47b53-115">E_POINTER</span></span>|<span data-ttu-id="47b53-116">`ppInterface` es null.</span><span class="sxs-lookup"><span data-stu-id="47b53-116">`ppInterface` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="47b53-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="47b53-117">Remarks</span></span>  
 <span data-ttu-id="47b53-118">En la tabla siguiente se muestran las combinaciones admitidas para `clsid` y `riid` .</span><span class="sxs-lookup"><span data-stu-id="47b53-118">The following table shows the supported combinations for `clsid` and `riid`.</span></span>  
  
|`clsid`|`riid`|  
|--------------|------------|  
|<span data-ttu-id="47b53-119">CLSID_CLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="47b53-119">CLSID_CLRMetaHost</span></span>|<span data-ttu-id="47b53-120">IID_ICLRMetaHost</span><span class="sxs-lookup"><span data-stu-id="47b53-120">IID_ICLRMetaHost</span></span>|  
|<span data-ttu-id="47b53-121">CLSID_CLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="47b53-121">CLSID_CLRMetaHostPolicy</span></span>|<span data-ttu-id="47b53-122">IID_ICLRMetaHostPolicy</span><span class="sxs-lookup"><span data-stu-id="47b53-122">IID_ICLRMetaHostPolicy</span></span>|  
|<span data-ttu-id="47b53-123">CLSID_CLRDebugging</span><span class="sxs-lookup"><span data-stu-id="47b53-123">CLSID_CLRDebugging</span></span>|<span data-ttu-id="47b53-124">IID_ICLRDebugging</span><span class="sxs-lookup"><span data-stu-id="47b53-124">IID_ICLRDebugging</span></span>|  
  
 <span data-ttu-id="47b53-125">En el código siguiente se muestra cómo usar `CLRCreateInstance` para obtener las tres interfaces:</span><span class="sxs-lookup"><span data-stu-id="47b53-125">The following code shows how to use `CLRCreateInstance` to get all three interfaces:</span></span>  
  
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
  
## <a name="requirements"></a><span data-ttu-id="47b53-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47b53-126">Requirements</span></span>  
 <span data-ttu-id="47b53-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47b53-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47b53-128">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="47b53-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="47b53-129">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="47b53-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="47b53-130">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47b53-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47b53-131">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="47b53-131">See also</span></span>

- [<span data-ttu-id="47b53-132">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="47b53-132">Hosting</span></span>](index.md)
