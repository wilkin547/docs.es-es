---
title: ICLRMetaHost::EnumerateLoadedRuntimes (Método)
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateLoadedRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateLoadedRuntimes
helpviewer_keywords:
- EnumerateLoadedRuntimes method [.NET Framework hosting]
- ICLRMetaHost::EnumerateLoadedRuntimes method [.NET Framework hosting]
ms.assetid: 22fc0a3f-dce4-4766-9a3c-9fab15f4b4ca
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0e1213128f5728f17225fbf6906d877dc64e86d
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59106618"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="3a89a-102">ICLRMetaHost::EnumerateLoadedRuntimes (Método)</span><span class="sxs-lookup"><span data-stu-id="3a89a-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="3a89a-103">Devuelve una enumeración que incluye válido [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) puntero de interfaz para cada versión de common language runtime (CLR) que se carga en un proceso determinado.</span><span class="sxs-lookup"><span data-stu-id="3a89a-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="3a89a-104">Este método reemplaza el [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="3a89a-104">This method supersedes the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3a89a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3a89a-105">Syntax</span></span>  
  
```  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3a89a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3a89a-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="3a89a-107">[in] El identificador del proceso para inspeccionar para carga los tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="3a89a-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="3a89a-108">[out] Un <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeración de [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces que corresponden a cada CLR cargada por el proceso.</span><span class="sxs-lookup"><span data-stu-id="3a89a-108">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3a89a-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3a89a-109">Return Value</span></span>  
 <span data-ttu-id="3a89a-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="3a89a-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="3a89a-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3a89a-111">HRESULT</span></span>|<span data-ttu-id="3a89a-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="3a89a-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="3a89a-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="3a89a-113">S_OK</span></span>|<span data-ttu-id="3a89a-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3a89a-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="3a89a-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="3a89a-115">E_POINTER</span></span>|<span data-ttu-id="3a89a-116">`ppEnumerator` es null.</span><span class="sxs-lookup"><span data-stu-id="3a89a-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3a89a-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3a89a-117">Remarks</span></span>  
 <span data-ttu-id="3a89a-118">Este método es cargar enumera todos los tiempos de ejecución, incluso si se cargaron con funciones desusadas como [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="3a89a-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3a89a-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3a89a-119">Requirements</span></span>  
 <span data-ttu-id="3a89a-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3a89a-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3a89a-121">**Encabezado**: MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="3a89a-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="3a89a-122">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3a89a-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="3a89a-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3a89a-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3a89a-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="3a89a-124">See also</span></span>

- [<span data-ttu-id="3a89a-125">ICLRMetaHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="3a89a-125">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="3a89a-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="3a89a-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
