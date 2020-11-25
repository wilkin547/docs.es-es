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
ms.openlocfilehash: 98184dd6ea16df066905039b028acd689ff3f290
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730440"
---
# <a name="iclrmetahostenumerateloadedruntimes-method"></a><span data-ttu-id="86d86-102">ICLRMetaHost::EnumerateLoadedRuntimes (Método)</span><span class="sxs-lookup"><span data-stu-id="86d86-102">ICLRMetaHost::EnumerateLoadedRuntimes Method</span></span>

<span data-ttu-id="86d86-103">Devuelve una enumeración que incluye un puntero de interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) válido para cada versión del Common Language Runtime (CLR) que se carga en un proceso determinado.</span><span class="sxs-lookup"><span data-stu-id="86d86-103">Returns an enumeration that includes a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface pointer for each version of the common language runtime (CLR) that is loaded in a given process.</span></span> <span data-ttu-id="86d86-104">Este método reemplaza a la función [GetVersionFromProcess (](getversionfromprocess-function.md) .</span><span class="sxs-lookup"><span data-stu-id="86d86-104">This method supersedes the [GetVersionFromProcess](getversionfromprocess-function.md) function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86d86-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="86d86-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateLoadedRuntimes (  
    [in] HANDLE hndProcess,  
    [out, retval] IEnumUnknown **ppEnumerator  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86d86-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="86d86-106">Parameters</span></span>  

 `hndProcess`  
 <span data-ttu-id="86d86-107">de Identificador del proceso para inspeccionar los tiempos de ejecución cargados.</span><span class="sxs-lookup"><span data-stu-id="86d86-107">[in] The handle of the process to inspect for loaded runtimes.</span></span>  
  
 `ppEnumerator`  
 <span data-ttu-id="86d86-108">enuncia Una <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeración de las interfaces [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) correspondientes a cada CLR que carga el proceso.</span><span class="sxs-lookup"><span data-stu-id="86d86-108">[out] An <xref:Microsoft.VisualStudio.OLE.Interop.IEnumUnknown> enumeration of [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interfaces corresponding to each CLR that is loaded by the process.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="86d86-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="86d86-109">Return Value</span></span>  

 <span data-ttu-id="86d86-110">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="86d86-110">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="86d86-111">HRESULT</span><span class="sxs-lookup"><span data-stu-id="86d86-111">HRESULT</span></span>|<span data-ttu-id="86d86-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="86d86-112">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="86d86-113">S_OK</span><span class="sxs-lookup"><span data-stu-id="86d86-113">S_OK</span></span>|<span data-ttu-id="86d86-114">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="86d86-114">The method completed successfully.</span></span>|  
|<span data-ttu-id="86d86-115">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="86d86-115">E_POINTER</span></span>|<span data-ttu-id="86d86-116">`ppEnumerator` es null.</span><span class="sxs-lookup"><span data-stu-id="86d86-116">`ppEnumerator` is null.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="86d86-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="86d86-117">Remarks</span></span>  

 <span data-ttu-id="86d86-118">Este método muestra todos los tiempos de ejecución cargados, incluso si se cargaron con funciones desusadas como [CorBindToRuntime](corbindtoruntime-function.md).</span><span class="sxs-lookup"><span data-stu-id="86d86-118">This method is lists all loaded runtimes, even if they were loaded with deprecated functions such as [CorBindToRuntime](corbindtoruntime-function.md).</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86d86-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="86d86-119">Requirements</span></span>  

 <span data-ttu-id="86d86-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="86d86-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86d86-121">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="86d86-121">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="86d86-122">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="86d86-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="86d86-123">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86d86-123">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86d86-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="86d86-124">See also</span></span>

- [<span data-ttu-id="86d86-125">ICLRMetaHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="86d86-125">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="86d86-126">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="86d86-126">Hosting</span></span>](index.md)
