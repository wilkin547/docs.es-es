---
title: "ICLRRuntimeInfo::GetProcAddress (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- ICLRRuntimeInfo.GetProcAddress
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRRuntimeInfo::GetProcAddress
helpviewer_keywords:
- GetProcAddress method [.NET Framework hosting]
- ICLRRuntimeInfo::GetProcAddress method [.NET Framework hosting]
ms.assetid: a7732bfc-689a-4926-88fd-4f81e6f9ed78
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 2878b23a2f848657e1d26b3bfb8395f8897c0632
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="c850a-102">ICLRRuntimeInfo::GetProcAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="c850a-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="c850a-103">Obtiene la dirección de una función especificada que se exportó desde common language runtime (CLR) asociado a esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="c850a-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="c850a-104">Este método reemplaza a la [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="c850a-104">This method supersedes the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c850a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c850a-105">Syntax</span></span>  
  
```  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="c850a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c850a-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="c850a-107">[in] El nombre de la función exportada.</span><span class="sxs-lookup"><span data-stu-id="c850a-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="c850a-108">[out] La dirección de la función exportada.</span><span class="sxs-lookup"><span data-stu-id="c850a-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c850a-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c850a-109">Return Value</span></span>  
 <span data-ttu-id="c850a-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="c850a-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="c850a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c850a-111">HRESULT</span></span>|<span data-ttu-id="c850a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="c850a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="c850a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="c850a-113">S_OK</span></span>|<span data-ttu-id="c850a-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c850a-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="c850a-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="c850a-115">E_POINTER</span></span>|<span data-ttu-id="c850a-116">`pszProcName` o `ppProc` es null.</span><span class="sxs-lookup"><span data-stu-id="c850a-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="c850a-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="c850a-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="c850a-118">La función especificada no es una función exportada.</span><span class="sxs-lookup"><span data-stu-id="c850a-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="c850a-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c850a-119">Remarks</span></span>  
 <span data-ttu-id="c850a-120">Este método hace que el CLR debe ser cargado pero no inicializado.</span><span class="sxs-lookup"><span data-stu-id="c850a-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="c850a-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c850a-121">Requirements</span></span>  
 <span data-ttu-id="c850a-122">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c850a-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c850a-123">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="c850a-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="c850a-124">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c850a-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="c850a-125">**Versiones de .NET framework:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c850a-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c850a-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="c850a-126">See Also</span></span>  
 [<span data-ttu-id="c850a-127">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c850a-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)  
 [<span data-ttu-id="c850a-128">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="c850a-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)  
 [<span data-ttu-id="c850a-129">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="c850a-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
