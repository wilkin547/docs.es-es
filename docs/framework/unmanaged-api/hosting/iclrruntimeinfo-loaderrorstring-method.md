---
title: ICLRRuntimeInfo::LoadErrorString (Método)
ms.date: 03/30/2017
api_name:
- ICLRRuntimeInfo.LoadErrorString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::LoadErrorString
helpviewer_keywords:
- ICLRRuntimeInfo::LoadErrorString method [.NET Framework hosting]
- LoadErrorString method [.NET Framework hosting]
ms.assetid: 52c543ab-9ef5-4ee7-b836-c0ffc35cd45b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd7bdcf891146a15953b7466e0f6dc680495bd5a
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2019
ms.locfileid: "64585058"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="991b5-102">ICLRRuntimeInfo::LoadErrorString (Método)</span><span class="sxs-lookup"><span data-stu-id="991b5-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="991b5-103">Convierte un valor HRESULT en un mensaje de error adecuado para la referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="991b5-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="991b5-104">Este método reemplaza las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="991b5-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="991b5-105">LoadStringRC</span><span class="sxs-lookup"><span data-stu-id="991b5-105">LoadStringRC</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrc-function.md)  
  
- [<span data-ttu-id="991b5-106">LoadStringRCEx</span><span class="sxs-lookup"><span data-stu-id="991b5-106">LoadStringRCEx</span></span>](../../../../docs/framework/unmanaged-api/hosting/loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="991b5-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="991b5-107">Syntax</span></span>  
  
```  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="991b5-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="991b5-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="991b5-109">[in] El valor HRESULT a traducir.</span><span class="sxs-lookup"><span data-stu-id="991b5-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="991b5-110">[out] La cadena de mensaje asociada con el valor HRESULT determinado.</span><span class="sxs-lookup"><span data-stu-id="991b5-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="991b5-111">[in, out] El tamaño de `pwzbuffer` para evitar saturaciones de búfer.</span><span class="sxs-lookup"><span data-stu-id="991b5-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="991b5-112">Si `pwzbuffer` es null, `pcchBuffer` proporciona el tamaño esperado de `pwzbuffer` para permitir la preasignación.</span><span class="sxs-lookup"><span data-stu-id="991b5-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="991b5-113">[in] El identificador de referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="991b5-113">[in] The culture identifier.</span></span> <span data-ttu-id="991b5-114">Para usar la referencia cultural predeterminada, debe especificar -1.</span><span class="sxs-lookup"><span data-stu-id="991b5-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="991b5-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="991b5-115">Return Value</span></span>  
 <span data-ttu-id="991b5-116">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="991b5-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="991b5-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="991b5-117">HRESULT</span></span>|<span data-ttu-id="991b5-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="991b5-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="991b5-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="991b5-119">S_OK</span></span>|<span data-ttu-id="991b5-120">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="991b5-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="991b5-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="991b5-121">E_POINTER</span></span>|<span data-ttu-id="991b5-122">`pcchBuffer` es null.</span><span class="sxs-lookup"><span data-stu-id="991b5-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="991b5-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="991b5-123">E_INVALIDARG</span></span>|<span data-ttu-id="991b5-124">`pwzBuffer` es null.</span><span class="sxs-lookup"><span data-stu-id="991b5-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="991b5-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="991b5-125">Requirements</span></span>  
 <span data-ttu-id="991b5-126">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="991b5-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="991b5-127">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="991b5-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="991b5-128">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="991b5-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="991b5-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="991b5-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="991b5-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="991b5-130">See also</span></span>

- [<span data-ttu-id="991b5-131">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="991b5-131">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="991b5-132">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="991b5-132">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="991b5-133">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="991b5-133">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
