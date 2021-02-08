---
description: 'Más información acerca de: ICLRMetaHost:: EnumerateLoadedRuntimes (método)'
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
ms.openlocfilehash: 508c4daca7e34366e0da35591f4e7a780301e823
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99789871"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="097e6-103">ICLRMetaHost::EnumerateLoadedRuntimes (Método)</span><span class="sxs-lookup"><span data-stu-id="097e6-103">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>

<span data-ttu-id="097e6-104">Devuelve una enumeración que incluye un puntero de interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) válido para cada versión del Common Language Runtime (CLR) que se carga en un proceso determinado.</span><span class="sxs-lookup"><span data-stu-id="097e6-104">Returns an enumeration that includes a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="097e6-105">Este método reemplaza a la función [GetVersionFromProcess (](getversionfromprocess-function.md) .</span><span class="sxs-lookup"><span data-stu-id="097e6-105">This method supersedes the [GetVersionFromProcess](getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="097e6-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="097e6-106">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="097e6-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="097e6-107">Parameters</span></span>  

 `hndProcess`  
 <span data-ttu-id="097e6-108">de Identificador del proceso para inspeccionar los tiempos de ejecución cargados.</span><span class="sxs-lookup"><span data-stu-id="097e6-108">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="097e6-109">enuncia Una <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeración de las interfaces [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) correspondientes a cada CLR que carga el proceso.</span><span class="sxs-lookup"><span data-stu-id="097e6-109">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="097e6-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="097e6-110">Return Value</span></span>  

 <span data-ttu-id="097e6-111">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="097e6-111">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="097e6-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="097e6-112">HRESULT</span></span>|<span data-ttu-id="097e6-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="097e6-113">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="097e6-114">S_OK</span><span class="sxs-lookup"><span data-stu-id="097e6-114">S_OK</span></span>|<span data-ttu-id="097e6-115">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="097e6-115">The method completed successfully.</span></span>|  
|<span data-ttu-id="097e6-116">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="097e6-116">E_POINTER</span></span>|<span data-ttu-id="097e6-117">`ppEnumerator` es null.</span><span class="sxs-lookup"><span data-stu-id="097e6-117">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="097e6-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="097e6-118">Remarks</span></span>  

 <span data-ttu-id="097e6-119">Este método muestra todos los tiempos de ejecución cargados, incluso si se cargaron con funciones desusadas como [CorBindToRuntime](corbindtoruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="097e6-119">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="097e6-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="097e6-120">Requirements</span></span>  

 <span data-ttu-id="097e6-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="097e6-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="097e6-122">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="097e6-122">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="097e6-123">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="097e6-123">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="097e6-124">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="097e6-124">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="097e6-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="097e6-125">See also</span></span>

- [<span data-ttu-id="097e6-126">ICLRMetaHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="097e6-126">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="097e6-127">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="097e6-127">Hosting</span></span>](index.md)
