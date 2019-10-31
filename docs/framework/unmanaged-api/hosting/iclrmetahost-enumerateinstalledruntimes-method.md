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
ms.openlocfilehash: 9415d5189edb901822abad9269e0150e7601a963
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140958"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a><span data-ttu-id="0c0c8-102">ICLRMetaHost::EnumerateInstalledRuntimes (Método)</span><span class="sxs-lookup"><span data-stu-id="0c0c8-102">ICLRMetaHost::EnumerateInstalledRuntimes Method</span></span>
<span data-ttu-id="0c0c8-103">Devuelve una enumeración que contiene una interfaz [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) válida para cada versión del Common Language Runtime (CLR) que está instalada en un equipo.</span><span class="sxs-lookup"><span data-stu-id="0c0c8-103">Returns an enumeration that contains a valid [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interface for each version of the common language runtime (CLR) that is installed on a computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0c0c8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c0c8-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0c0c8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0c0c8-105">Parameters</span></span>  
 `ppEnumerator`  
 <span data-ttu-id="0c0c8-106">enuncia Una enumeración de las interfaces [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) correspondientes a cada versión de CLR que está instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="0c0c8-106">[out] An enumeration of [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-interface.md) interfaces corresponding to each version of the CLR that is installed on the computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="0c0c8-107">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="0c0c8-107">Return Value</span></span>  
 <span data-ttu-id="0c0c8-108">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="0c0c8-108">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="0c0c8-109">HRESULT</span><span class="sxs-lookup"><span data-stu-id="0c0c8-109">HRESULT</span></span>|<span data-ttu-id="0c0c8-110">Descripción</span><span class="sxs-lookup"><span data-stu-id="0c0c8-110">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="0c0c8-111">S_OK</span><span class="sxs-lookup"><span data-stu-id="0c0c8-111">S_OK</span></span>|<span data-ttu-id="0c0c8-112">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="0c0c8-112">The method completed successfully.</span></span>|  
|<span data-ttu-id="0c0c8-113">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="0c0c8-113">E_POINTER</span></span>|<span data-ttu-id="0c0c8-114">`ppEnumerator` es null.</span><span class="sxs-lookup"><span data-stu-id="0c0c8-114">`ppEnumerator` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="0c0c8-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c0c8-115">Requirements</span></span>  
 <span data-ttu-id="0c0c8-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0c0c8-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0c0c8-117">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="0c0c8-117">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="0c0c8-118">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="0c0c8-118">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="0c0c8-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0c0c8-119">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c0c8-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c0c8-120">See also</span></span>

- [<span data-ttu-id="0c0c8-121">ICLRMetaHost (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0c0c8-121">ICLRMetaHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [<span data-ttu-id="0c0c8-122">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="0c0c8-122">Hosting</span></span>](../../../../docs/framework/unmanaged-api/hosting/index.md)
