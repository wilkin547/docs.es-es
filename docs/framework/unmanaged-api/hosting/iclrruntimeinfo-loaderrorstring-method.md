---
description: 'Más información acerca de: ICLRRuntimeInfo:: LoadErrorString ((método)'
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
ms.openlocfilehash: 0523b5b89072db50c83c52065c22e9df7167a027
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785073"
---
# <a name="iclrruntimeinfoloaderrorstring-method"></a><span data-ttu-id="578ec-103">ICLRRuntimeInfo::LoadErrorString (Método)</span><span class="sxs-lookup"><span data-stu-id="578ec-103">ICLRRuntimeInfo::LoadErrorString Method</span></span>

<span data-ttu-id="578ec-104">Convierte un valor HRESULT en un mensaje de error adecuado para la referencia cultural especificada.</span><span class="sxs-lookup"><span data-stu-id="578ec-104">Translates an HRESULT value into an appropriate error message for the specified culture.</span></span>  
  
 <span data-ttu-id="578ec-105">Este método sustituye a las siguientes funciones:</span><span class="sxs-lookup"><span data-stu-id="578ec-105">This method supersedes the following functions:</span></span>  
  
- [<span data-ttu-id="578ec-106">Loadstringrc (</span><span class="sxs-lookup"><span data-stu-id="578ec-106">LoadStringRC</span></span>](loadstringrc-function.md)  
  
- [<span data-ttu-id="578ec-107">Loadstringrcex (</span><span class="sxs-lookup"><span data-stu-id="578ec-107">LoadStringRCEx</span></span>](loadstringrcex-function.md)  
  
## <a name="syntax"></a><span data-ttu-id="578ec-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="578ec-108">Syntax</span></span>  
  
```cpp  
HRESULT LoadErrorString(  
     [in] UINT iResourceID,  
     [out, size_is(*pcchBuffer)] LPWSTR pwzBuffer,  
     [in, out]  DWORD *pcchBuffer,  
     [in, lcid] LONG iLocaleID);  
```  
  
## <a name="parameters"></a><span data-ttu-id="578ec-109">Parámetros</span><span class="sxs-lookup"><span data-stu-id="578ec-109">Parameters</span></span>  

 `iResourceID`  
 <span data-ttu-id="578ec-110">de HRESULT que se va a traducir.</span><span class="sxs-lookup"><span data-stu-id="578ec-110">[in] The HRESULT to translate.</span></span>  
  
 `pwzBuffer`  
 <span data-ttu-id="578ec-111">enuncia Cadena de mensaje asociada al HRESULT especificado.</span><span class="sxs-lookup"><span data-stu-id="578ec-111">[out] The message string associated with the given HRESULT.</span></span>  
  
 `pcchBuffer`  
 <span data-ttu-id="578ec-112">[in, out] Tamaño de `pwzbuffer` para evitar las saturaciones del búfer.</span><span class="sxs-lookup"><span data-stu-id="578ec-112">[in, out] The size of `pwzbuffer` to avoid buffer overruns.</span></span> <span data-ttu-id="578ec-113">Si `pwzbuffer` es null, `pcchBuffer` proporciona el tamaño esperado de `pwzbuffer` para permitir la asignación previa.</span><span class="sxs-lookup"><span data-stu-id="578ec-113">If `pwzbuffer` is null, `pcchBuffer` provides the expected size of `pwzbuffer` to allow preallocation.</span></span>  
  
 `iLocaleID`  
 <span data-ttu-id="578ec-114">de Identificador de referencia cultural.</span><span class="sxs-lookup"><span data-stu-id="578ec-114">[in] The culture identifier.</span></span> <span data-ttu-id="578ec-115">Para utilizar la referencia cultural predeterminada, debe especificar-1.</span><span class="sxs-lookup"><span data-stu-id="578ec-115">To use the default culture, you must specify -1.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="578ec-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="578ec-116">Return Value</span></span>  

 <span data-ttu-id="578ec-117">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="578ec-117">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="578ec-118">HRESULT</span><span class="sxs-lookup"><span data-stu-id="578ec-118">HRESULT</span></span>|<span data-ttu-id="578ec-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="578ec-119">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="578ec-120">S_OK</span><span class="sxs-lookup"><span data-stu-id="578ec-120">S_OK</span></span>|<span data-ttu-id="578ec-121">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="578ec-121">The method completed successfully.</span></span>|  
|<span data-ttu-id="578ec-122">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="578ec-122">E_POINTER</span></span>|<span data-ttu-id="578ec-123">`pcchBuffer` es null.</span><span class="sxs-lookup"><span data-stu-id="578ec-123">`pcchBuffer` is null.</span></span>|  
|<span data-ttu-id="578ec-124">E_INVALIDARG</span><span class="sxs-lookup"><span data-stu-id="578ec-124">E_INVALIDARG</span></span>|<span data-ttu-id="578ec-125">`pwzBuffer` es null.</span><span class="sxs-lookup"><span data-stu-id="578ec-125">`pwzBuffer` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="578ec-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="578ec-126">Requirements</span></span>  

 <span data-ttu-id="578ec-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="578ec-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="578ec-128">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="578ec-128">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="578ec-129">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="578ec-129">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="578ec-130">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="578ec-130">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="578ec-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="578ec-131">See also</span></span>

- [<span data-ttu-id="578ec-132">ICLRRuntimeInfo (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="578ec-132">ICLRRuntimeInfo Interface</span></span>](iclrruntimeinfo-interface.md)
- [<span data-ttu-id="578ec-133">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="578ec-133">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="578ec-134">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="578ec-134">Hosting</span></span>](index.md)
