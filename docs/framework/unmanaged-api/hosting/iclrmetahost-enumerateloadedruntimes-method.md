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
ms.openlocfilehash: db10b5c67a098cc34292a2680bd832f9cef2861b
ms.sourcegitcommit: 3ab9254890a52a50762995fa6d7d77a00348db7e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/19/2018
ms.locfileid: "46323409"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="43b74-102">ICLRMetaHost::EnumerateLoadedRuntimes (Método)</span><span class="sxs-lookup"><span data-stu-id="43b74-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>
<span data-ttu-id="43b74-103">Devuelve una enumeración que incluye válido [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) puntero de interfaz para cada versión de common language runtime (CLR) que se carga en un proceso determinado.</span><span class="sxs-lookup"><span data-stu-id="43b74-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="43b74-104">Este método reemplaza el [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) función.</span><span class="sxs-lookup"><span data-stu-id="43b74-104">This method supersedes the [GetVersionFromProcess](../../../../docs/framework/unmanaged-api/hosting/getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="43b74-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="43b74-105">Syntax</span></span>  
  
```  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="43b74-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="43b74-106">Parameters</span></span>  
 `hndProcess`  
 <span data-ttu-id="43b74-107">[in] El identificador del proceso para inspeccionar para carga los tiempos de ejecución.</span><span class="sxs-lookup"><span data-stu-id="43b74-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="43b74-108">[out] Un <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeración de [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces que corresponden a cada CLR cargada por el proceso.</span><span class="sxs-lookup"><span data-stu-id="43b74-108">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="43b74-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="43b74-109">Return Value</span></span>  
 <span data-ttu-id="43b74-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="43b74-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="43b74-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="43b74-111">HRESULT</span></span>|<span data-ttu-id="43b74-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="43b74-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="43b74-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="43b74-113">S_OK</span></span>|<span data-ttu-id="43b74-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="43b74-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="43b74-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="43b74-115">E_POINTER</span></span>|<span data-ttu-id="43b74-116">`ppEnumerator` es null.</span><span class="sxs-lookup"><span data-stu-id="43b74-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="43b74-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="43b74-117">Remarks</span></span>  
 <span data-ttu-id="43b74-118">Este método es cargar enumera todos los tiempos de ejecución, incluso si se cargaron con funciones desusadas como [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="43b74-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="43b74-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="43b74-119">Requirements</span></span>  
 <span data-ttu-id="43b74-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="43b74-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="43b74-121">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="43b74-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="43b74-122">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="43b74-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="43b74-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="43b74-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43b74-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="43b74-124">See Also</span></span>  
 [<span data-ttu-id="43b74-125">ICLRMetaHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="43b74-125">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="43b74-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="43b74-126">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
