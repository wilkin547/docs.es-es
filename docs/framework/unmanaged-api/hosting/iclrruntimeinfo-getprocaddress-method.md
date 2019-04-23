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
ms.openlocfilehash: a95b6b7e20bbcd86dedf187c932f2cf74d37cdab
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59199185"
---
# <a name="iclrruntimeinfogetprocaddress-method"></a><span data-ttu-id="b6b42-102">ICLRRuntimeInfo::GetProcAddress (Método)</span><span class="sxs-lookup"><span data-stu-id="b6b42-102">ICLRRuntimeInfo::GetProcAddress Method</span></span>
<span data-ttu-id="b6b42-103">Obtiene la dirección de una función especificada que se exportó desde common language runtime (CLR) asociado a esta interfaz.</span><span class="sxs-lookup"><span data-stu-id="b6b42-103">Gets the address of a specified function that was exported from the common language runtime (CLR) associated with this interface.</span></span>  
  
 <span data-ttu-id="b6b42-104">Este método reemplaza el [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="b6b42-104">This method supersedes the [GetRealProcAddress](../../../../docs/framework/unmanaged-api/hosting/getrealprocaddress-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b6b42-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6b42-105">Syntax</span></span>  
  
```  
HRESULT GetProcAddress(  
     [in]  LPCSTR pszProcName,  
     [out, retval] LPVOID *ppProc);  
```  
  
## <a name="parameters"></a><span data-ttu-id="b6b42-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b6b42-106">Parameters</span></span>  
 `pszProcName`  
 <span data-ttu-id="b6b42-107">[in] El nombre de la función exportada.</span><span class="sxs-lookup"><span data-stu-id="b6b42-107">[in] The name of the exported function.</span></span>  
  
 `ppProc`  
 <span data-ttu-id="b6b42-108">[out] La dirección de la función exportada.</span><span class="sxs-lookup"><span data-stu-id="b6b42-108">[out] The address of the exported function.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="b6b42-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b6b42-109">Return Value</span></span>  
 <span data-ttu-id="b6b42-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="b6b42-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="b6b42-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="b6b42-111">HRESULT</span></span>|<span data-ttu-id="b6b42-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="b6b42-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="b6b42-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="b6b42-113">S_OK</span></span>|<span data-ttu-id="b6b42-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="b6b42-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="b6b42-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="b6b42-115">E_POINTER</span></span>|<span data-ttu-id="b6b42-116">`pszProcName` o `ppProc` es null.</span><span class="sxs-lookup"><span data-stu-id="b6b42-116">`pszProcName` or `ppProc` is null.</span></span>|  
|<span data-ttu-id="b6b42-117">CLR_E_SHIM_RUNTIMEEXPORT</span><span class="sxs-lookup"><span data-stu-id="b6b42-117">CLR_E_SHIM_RUNTIMEEXPORT</span></span>|<span data-ttu-id="b6b42-118">La función especificada no es una función exportada.</span><span class="sxs-lookup"><span data-stu-id="b6b42-118">The specified function is not an exported function.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="b6b42-119">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b6b42-119">Remarks</span></span>  
 <span data-ttu-id="b6b42-120">Este método provoca que el CLR que se cargó, pero no inicializado.</span><span class="sxs-lookup"><span data-stu-id="b6b42-120">This method causes the CLR to be loaded but not initialized.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="b6b42-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6b42-121">Requirements</span></span>  
 <span data-ttu-id="b6b42-122">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6b42-122">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b6b42-123">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="b6b42-123">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="b6b42-124">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b6b42-124">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="b6b42-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6b42-125">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b6b42-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6b42-126">See also</span></span>

- [<span data-ttu-id="b6b42-127">ICLRRuntimeInfo (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6b42-127">ICLRRuntimeInfo Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md)
- [<span data-ttu-id="b6b42-128">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="b6b42-128">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="b6b42-129">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="b6b42-129">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
