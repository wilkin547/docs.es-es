---
title: "ICLRRuntimeInfo::GetProcAddress (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICLRRuntimeInfo.GetProcAddress
api_location: mscoree.dll
api_type: COM
f1_keywords: ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: e1b8af06a52a3961bb3e551375350dee849343b3
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="76ac1-102">ICLRRuntimeInfo::GetProcAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="76ac1-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="76ac1-103">Obtiene la dirección de una función especificada que se exportó desde common language runtime (CLR) asociado a esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="76ac1-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="76ac1-104">Este método reemplaza a la [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="76ac1-104">This method supersedes the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="76ac1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="76ac1-105">Syntax</span></span>  
  
```  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="76ac1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="76ac1-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="76ac1-107">[in] El nombre de la función exportada.</span><span class="sxs-lookup"><span data-stu-id="76ac1-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="76ac1-108">[out] La dirección de la función exportada.</span><span class="sxs-lookup"><span data-stu-id="76ac1-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="76ac1-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="76ac1-109">Return Value</span></span>  
 <span data-ttu-id="76ac1-110">Este método devuelve los siguientes HRESULT específicos así como los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="76ac1-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="76ac1-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="76ac1-111">HRESULT</span></span>|<span data-ttu-id="76ac1-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="76ac1-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="76ac1-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="76ac1-113">S_OK</span></span>|<span data-ttu-id="76ac1-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="76ac1-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="76ac1-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="76ac1-115">E_POINTER</span></span>|<span data-ttu-id="76ac1-116">`pszProcName` o `ppProc` es null.</span><span class="sxs-lookup"><span data-stu-id="76ac1-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="76ac1-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="76ac1-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="76ac1-118">La función especificada no es una función exportada.</span><span class="sxs-lookup"><span data-stu-id="76ac1-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="76ac1-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="76ac1-119">Remarks</span></span>  
 <span data-ttu-id="76ac1-120">Este método hace que el CLR debe ser cargado pero no inicializado.</span><span class="sxs-lookup"><span data-stu-id="76ac1-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="76ac1-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="76ac1-121">Requirements</span></span>  
 <span data-ttu-id="76ac1-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="76ac1-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="76ac1-123">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="76ac1-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="76ac1-124">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="76ac1-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="76ac1-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="76ac1-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="76ac1-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="76ac1-126">See Also</span></span>  
 [<span data-ttu-id="76ac1-127">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="76ac1-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="76ac1-128">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="76ac1-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="76ac1-129">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="76ac1-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
