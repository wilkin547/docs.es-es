---
title: "ICLRRuntimeInfo::LoadErrorString (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.LoadErrorString
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 26fa051e5c4735307edbb443e6615a57190c0ae5
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="caafb-102">ICLRRuntimeInfo::LoadErrorString (Método)</span><span class="sxs-lookup"><span data-stu-id="caafb-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="caafb-103">Convierte un valor HRESULT en un mensaje de error adecuado para la referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="caafb-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="caafb-104">Este método reemplaza las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="caafb-104">This method supersedes the following functions:</span></span>  
  
-   [<span data-ttu-id="caafb-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="caafb-105">LoadStringRC</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
-   [<span data-ttu-id="caafb-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="caafb-106">LoadStringRCEx</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="caafb-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="caafb-107">Syntax</span></span>  
  
```  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="caafb-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="caafb-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="caafb-109">[in] HRESULT que se va a traducir.</span><span class="sxs-lookup"><span data-stu-id="caafb-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="caafb-110">[out] La cadena de mensaje asociada con el valor HRESULT determinado.</span><span class="sxs-lookup"><span data-stu-id="caafb-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="caafb-111">[entrada, salida] El tamaño de `pwzbuffer` para evitar saturaciones del búfer.</span><span class="sxs-lookup"><span data-stu-id="caafb-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="caafb-112">Si `pwzbuffer` es null, `pcchBuffer` proporciona el tamaño esperado de `pwzbuffer` para permitir la preasignación.</span><span class="sxs-lookup"><span data-stu-id="caafb-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="caafb-113">[in] El identificador de referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="caafb-113">[in] The culture identifier.</span></span> <span data-ttu-id="caafb-114">Para usar la referencia cultural predeterminada, debe especificar -1.</span><span class="sxs-lookup"><span data-stu-id="caafb-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="caafb-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="caafb-115">Return Value</span></span>  
 <span data-ttu-id="caafb-116">Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="caafb-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="caafb-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="caafb-117">HRESULT</span></span>|<span data-ttu-id="caafb-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="caafb-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="caafb-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="caafb-119">S_OK</span></span>|<span data-ttu-id="caafb-120">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="caafb-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="caafb-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="caafb-121">E_POINTER</span></span>|<span data-ttu-id="caafb-122">`pcchBuffer` es null.</span><span class="sxs-lookup"><span data-stu-id="caafb-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="caafb-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="caafb-123">E_INVALIDARG</span></span>|<span data-ttu-id="caafb-124">`pwzBuffer` es null.</span><span class="sxs-lookup"><span data-stu-id="caafb-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="caafb-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="caafb-125">Requirements</span></span>  
 <span data-ttu-id="caafb-126">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="caafb-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="caafb-127">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="caafb-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="caafb-128">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="caafb-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="caafb-129">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="caafb-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="caafb-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="caafb-130">See Also</span></span>  
 [<span data-ttu-id="caafb-131">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="caafb-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="caafb-132">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="caafb-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="caafb-133">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="caafb-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
