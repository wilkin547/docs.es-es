---
title: ICLRMetaHost::EnumerateInstalledRuntimes (Método)
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.EnumerateInstalledRuntimes
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes
helpviewer_keywords:
- ICLRMetaHost::EnumerateInstalledRuntimes method [.NET Framework hosting]
- EnumerateInstalledRuntimes method [.NET Framework hosting]
ms.assetid: 9e359384-0d3d-451c-807e-5d7fcebf2be7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ed4c09d910db6fa2e61d44e4ac777f9b6095a20
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33434286"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a><span data-ttu-id="8399d-102">ICLRMetaHost::EnumerateInstalledRuntimes (Método)</span><span class="sxs-lookup"><span data-stu-id="8399d-102">ICLRMetaHost::EnumerateInstalledRuntimes Method</span></span>
<span data-ttu-id="8399d-103">Devuelve una enumeración que contiene un válido [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaz para cada versión de common language runtime (CLR) que se instala en un equipo.</span><span class="sxs-lookup"><span data-stu-id="8399d-103">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface for each version of the common language runtime (CLR) that is installed on a computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8399d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8399d-104">Syntax</span></span>  
  
```  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8399d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8399d-105">Parameters</span></span>  
 `ppEnumerator`  
 <span data-ttu-id="8399d-106">[out] Una enumeración de [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces correspondientes a cada versión de CLR que está instalado en el equipo.</span><span class="sxs-lookup"><span data-stu-id="8399d-106">[out] An enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each version of the CLR that is installed on the computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8399d-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8399d-107">Return Value</span></span>  
 <span data-ttu-id="8399d-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="8399d-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="8399d-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8399d-109">HRESULT</span></span>|<span data-ttu-id="8399d-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="8399d-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="8399d-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="8399d-111">S_OK</span></span>|<span data-ttu-id="8399d-112">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="8399d-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="8399d-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="8399d-113">E_POINTER</span></span>|<span data-ttu-id="8399d-114">`ppEnumerator` es null.</span><span class="sxs-lookup"><span data-stu-id="8399d-114">`ppEnumerator` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8399d-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8399d-115">Requirements</span></span>  
 <span data-ttu-id="8399d-116">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8399d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8399d-117">**Encabezado:** MetaHost.h</span><span class="sxs-lookup"><span data-stu-id="8399d-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="8399d-118">**Biblioteca:** incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8399d-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8399d-119">**Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8399d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8399d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="8399d-120">See Also</span></span>  
 [<span data-ttu-id="8399d-121">ICLRMetaHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8399d-121">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [<span data-ttu-id="8399d-122">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="8399d-122">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
