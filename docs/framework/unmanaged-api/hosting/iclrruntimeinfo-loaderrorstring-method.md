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
ms.openlocfilehash: da6efae38cd70a68feea56b12e86be23fde7f0cb
ms.sourcegitcommit: c76c8b2c39ed2f0eee422b61a2ab4c05ca7771fa
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/21/2020
ms.locfileid: "83762193"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="03d3c-102">ICLRRuntimeInfo::LoadErrorString (Método)</span><span class="sxs-lookup"><span data-stu-id="03d3c-102">ICLRRuntimeInfo::LoadErrorString Method</span></span>
<span data-ttu-id="03d3c-103">Convierte un valor HRESULT en un mensaje de error adecuado para la referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="03d3c-103">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="03d3c-104">Este método sustituye a las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="03d3c-104">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="03d3c-105">Loadstringrc (</span><span class="sxs-lookup"><span data-stu-id="03d3c-105">LoadStringRC</span></span>](loadstringrc-function.md)  
  
- [<span data-ttu-id="03d3c-106">Loadstringrcex (</span><span class="sxs-lookup"><span data-stu-id="03d3c-106">LoadStringRCEx</span></span>](loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="03d3c-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03d3c-107">Syntax</span></span>  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03d3c-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03d3c-108">Parameters</span></span>  
 `iResourceID`  
 <span data-ttu-id="03d3c-109">de HRESULT que se va a traducir.</span><span class="sxs-lookup"><span data-stu-id="03d3c-109">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="03d3c-110">enuncia Cadena de mensaje asociada al HRESULT especificado.</span><span class="sxs-lookup"><span data-stu-id="03d3c-110">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="03d3c-111">[in, out] Tamaño de `pwzbuffer` para evitar las saturaciones del búfer.</span><span class="sxs-lookup"><span data-stu-id="03d3c-111">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="03d3c-112">Si `pwzbuffer` es null, `pcchBuffer` proporciona el tamaño esperado de `pwzbuffer` para permitir la asignación previa.</span><span class="sxs-lookup"><span data-stu-id="03d3c-112">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="03d3c-113">de Identificador de referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="03d3c-113">[in] The culture identifier.</span></span> <span data-ttu-id="03d3c-114">Para utilizar la referencia cultural predeterminada, debe especificar-1.</span><span class="sxs-lookup"><span data-stu-id="03d3c-114">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="03d3c-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="03d3c-115">Return Value</span></span>  
 <span data-ttu-id="03d3c-116">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="03d3c-116">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="03d3c-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="03d3c-117">HRESULT</span></span>|<span data-ttu-id="03d3c-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="03d3c-118">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="03d3c-119">S_OK</span><span class="sxs-lookup"><span data-stu-id="03d3c-119">S_OK</span></span>|<span data-ttu-id="03d3c-120">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="03d3c-120">The method completed successfully.</span></span>|  
|<span data-ttu-id="03d3c-121">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="03d3c-121">E_POINTER</span></span>|<span data-ttu-id="03d3c-122">`pcchBuffer` es null.</span><span class="sxs-lookup"><span data-stu-id="03d3c-122">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="03d3c-123">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="03d3c-123">E_INVALIDARG</span></span>|<span data-ttu-id="03d3c-124">`pwzBuffer` es null.</span><span class="sxs-lookup"><span data-stu-id="03d3c-124">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="03d3c-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03d3c-125">Requirements</span></span>  
 <span data-ttu-id="03d3c-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03d3c-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03d3c-127">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="03d3c-127">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="03d3c-128">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="03d3c-128">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="03d3c-129">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03d3c-129">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03d3c-130">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="03d3c-130">See also</span></span>

- [<span data-ttu-id="03d3c-131">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="03d3c-131">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="03d3c-132">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="03d3c-132">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="03d3c-133">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="03d3c-133">Hosting</span></span>](index.md)
