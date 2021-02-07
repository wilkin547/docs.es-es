---
description: 'Más información acerca de: ICLRMetaHost:: Enumerateinstalledruntimes ((método)'
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
ms.openlocfilehash: a1c2fe46a64339e013df0f65dc073d183036a0fb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689201"
---
# <a name="iclrmetahostenumerateinstalledruntimes-method"></a><span data-ttu-id="48f94-103">ICLRMetaHost::EnumerateInstalledRuntimes (Método)</span><span class="sxs-lookup"><span data-stu-id="48f94-103">ICLRMetaHost::EnumerateInstalledRuntimes Method</span></span>

<span data-ttu-id="48f94-104">Devuelve una enumeración que contiene una interfaz [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) válida para cada versión del Common Language Runtime (CLR) que está instalada en un equipo.</span><span class="sxs-lookup"><span data-stu-id="48f94-104">Returns an enumeration that contains a valid [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interface for each version of the common language runtime (CLR) that is installed on a computer.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="48f94-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="48f94-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumerateInstalledRuntimes (  
    [out, retval] IEnumUnknown **ppEnumerator);  
```  
  
## <a name="parameters"></a><span data-ttu-id="48f94-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="48f94-106">Parameters</span></span>  

 `ppEnumerator`  
 <span data-ttu-id="48f94-107">enuncia Una enumeración de las interfaces [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) correspondientes a cada versión de CLR que está instalada en el equipo.</span><span class="sxs-lookup"><span data-stu-id="48f94-107">[out] An enumeration of [ICLRRuntimeInfo](iclrruntimeinfo-interface.md) interfaces corresponding to each version of the CLR that is installed on the computer.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="48f94-108">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="48f94-108">Return Value</span></span>  

 <span data-ttu-id="48f94-109">Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.</span><span class="sxs-lookup"><span data-stu-id="48f94-109">This method returns the following specific HRESULTs as well as HRESULT errors that indicate method failure.</span></span>  
  
|<span data-ttu-id="48f94-110">HRESULT</span><span class="sxs-lookup"><span data-stu-id="48f94-110">HRESULT</span></span>|<span data-ttu-id="48f94-111">Descripción</span><span class="sxs-lookup"><span data-stu-id="48f94-111">Description</span></span>|  
|-------------|-----------------|  
|<span data-ttu-id="48f94-112">S_OK</span><span class="sxs-lookup"><span data-stu-id="48f94-112">S_OK</span></span>|<span data-ttu-id="48f94-113">El método se completó correctamente.</span><span class="sxs-lookup"><span data-stu-id="48f94-113">The method completed successfully.</span></span>|  
|<span data-ttu-id="48f94-114">E_POINTER</span><span class="sxs-lookup"><span data-stu-id="48f94-114">E_POINTER</span></span>|<span data-ttu-id="48f94-115">`ppEnumerator` es null.</span><span class="sxs-lookup"><span data-stu-id="48f94-115">`ppEnumerator` is null.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="48f94-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="48f94-116">Requirements</span></span>  

 <span data-ttu-id="48f94-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="48f94-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="48f94-118">**Encabezado:** Metahost. h</span><span class="sxs-lookup"><span data-stu-id="48f94-118">**Header:** MetaHost.h</span></span>  
  
 <span data-ttu-id="48f94-119">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="48f94-119">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="48f94-120">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="48f94-120">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="48f94-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="48f94-121">See also</span></span>

- [<span data-ttu-id="48f94-122">ICLRMetaHost (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="48f94-122">ICLRMetaHost Interface</span></span>](iclrmetahost-interface.md)
- [<span data-ttu-id="48f94-123">Hospedar aplicaciones de WPF</span><span class="sxs-lookup"><span data-stu-id="48f94-123">Hosting</span></span>](index.md)
