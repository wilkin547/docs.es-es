---
title: "CoEEShutDownCOM (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: CoEEShutDownCOM
helpviewer_keywords: CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type: apiref
caps.latest.revision: "18"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 0ae339310c2bfd186cae798ff603d69735abeefd
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="8bbe8-102">CoEEShutDownCOM (Función)</span><span class="sxs-lookup"><span data-stu-id="8bbe8-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="8bbe8-103">Obliga a common language runtime (CLR) para liberar todos los punteros de interfaz que tiene en los contenedores invocables en tiempo de ejecución (RCW).</span><span class="sxs-lookup"><span data-stu-id="8bbe8-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="8bbe8-104">Esto tiene el efecto de liberar todas las cachés RCW.</span><span class="sxs-lookup"><span data-stu-id="8bbe8-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="8bbe8-105">Esta función global está desusada en la [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8bbe8-105">This global function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="8bbe8-106">En su lugar, utilice el punto de entrada para un runtime concreto.</span><span class="sxs-lookup"><span data-stu-id="8bbe8-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8bbe8-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8bbe8-107">Syntax</span></span>  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="8bbe8-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8bbe8-108">Remarks</span></span>  
 <span data-ttu-id="8bbe8-109">El `CoEEShutDownCOM` función primero libera todos los RCW en todos los contextos y en todas las memorias caché y, a continuación, quita cualquier notificación de anulación existente en el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="8bbe8-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="8bbe8-110">Se produce ninguna descarga de DLL.</span><span class="sxs-lookup"><span data-stu-id="8bbe8-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="8bbe8-111">Esta función afecta a todos los runtimes que se cargan en el proceso.</span><span class="sxs-lookup"><span data-stu-id="8bbe8-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="8bbe8-112">A partir del [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], llame al punto de entrada para esta función en el tiempo de ejecución específico que desea que se vea afectada.</span><span class="sxs-lookup"><span data-stu-id="8bbe8-112">Beginning with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="8bbe8-113">Para obtener el punto de entrada, llame a la [ICLRRuntimeInfo:: GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) método y especifique "CoEEShutDownCOM".</span><span class="sxs-lookup"><span data-stu-id="8bbe8-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8bbe8-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8bbe8-114">Requirements</span></span>  
 <span data-ttu-id="8bbe8-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bbe8-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bbe8-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="8bbe8-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8bbe8-117">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8bbe8-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8bbe8-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8bbe8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bbe8-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="8bbe8-119">See Also</span></span>  
 [<span data-ttu-id="8bbe8-120">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="8bbe8-120">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
