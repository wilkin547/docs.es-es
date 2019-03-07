---
title: ICLRRuntimeInfo::GetProcAddress (Método)
ms.date: 03/30/2017
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: da9ae70056e3ef5d6d9e03fde1dcf8775e5d118e
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57498957"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="787c8-102">ICLRRuntimeInfo::GetProcAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="787c8-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="787c8-103">Obtiene la dirección de una función especificada que se exportó desde common language runtime (CLR) asociado a esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="787c8-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="787c8-104">Este método reemplaza el [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="787c8-104">This method supersedes the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="787c8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="787c8-105">Syntax</span></span>  
  
```  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="787c8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="787c8-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="787c8-107">[in] El nombre de la función exportada.</span><span class="sxs-lookup"><span data-stu-id="787c8-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="787c8-108">[out] La dirección de la función exportada.</span><span class="sxs-lookup"><span data-stu-id="787c8-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="787c8-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="787c8-109">Return Value</span></span>  
 <span data-ttu-id="787c8-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="787c8-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="787c8-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="787c8-111">HRESULT</span></span>|<span data-ttu-id="787c8-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="787c8-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="787c8-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="787c8-113">S_OK</span></span>|<span data-ttu-id="787c8-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="787c8-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="787c8-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="787c8-115">E_POINTER</span></span>|<span data-ttu-id="787c8-116">`pszProcName` o `ppProc` es null.</span><span class="sxs-lookup"><span data-stu-id="787c8-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="787c8-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="787c8-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="787c8-118">La función especificada no es una función exportada.</span><span class="sxs-lookup"><span data-stu-id="787c8-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="787c8-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="787c8-119">Remarks</span></span>  
 <span data-ttu-id="787c8-120">Este método provoca que el CLR que se cargó, pero no inicializado.</span><span class="sxs-lookup"><span data-stu-id="787c8-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="787c8-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="787c8-121">Requirements</span></span>  
 <span data-ttu-id="787c8-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="787c8-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="787c8-123">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="787c8-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="787c8-124">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="787c8-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="787c8-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="787c8-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="787c8-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="787c8-126">See also</span></span>
- [<span data-ttu-id="787c8-127">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="787c8-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="787c8-128">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="787c8-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="787c8-129">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="787c8-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
