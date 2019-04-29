---
title: CoEEShutDownCOM (Función)
ms.date: 03/30/2017
api_name:
- CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoEEShutDownCOM
helpviewer_keywords:
- CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8ddef35b1b707cc5c962402e880923dca7d4d9d6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789654"
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="11824-102">CoEEShutDownCOM (Función)</span><span class="sxs-lookup"><span data-stu-id="11824-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="11824-103">Obliga a common language runtime (CLR) para liberar todos los punteros de interfaz que tiene en los contenedores RCW (RCW).</span><span class="sxs-lookup"><span data-stu-id="11824-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="11824-104">Esto tiene el efecto de liberar todas las cachés RCW.</span><span class="sxs-lookup"><span data-stu-id="11824-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="11824-105">Esta función global está en desuso en el [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span><span class="sxs-lookup"><span data-stu-id="11824-105">This global function is deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span> <span data-ttu-id="11824-106">En su lugar, use el punto de entrada para un tiempo de ejecución específico.</span><span class="sxs-lookup"><span data-stu-id="11824-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11824-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11824-107">Syntax</span></span>  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="11824-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="11824-108">Remarks</span></span>  
 <span data-ttu-id="11824-109">El `CoEEShutDownCOM` función primero libera todos los RCW en todos los contextos y en todas las memorias caché y, a continuación, quita cualquier notificación de anulación existente en el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="11824-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="11824-110">Se produce ninguna descarga del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="11824-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="11824-111">Esta función afecta a todos los runtimes que se cargan en el proceso.</span><span class="sxs-lookup"><span data-stu-id="11824-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="11824-112">A partir del [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], llame al punto de entrada para esta función en el tiempo de ejecución específico que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="11824-112">Beginning with the [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)], call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="11824-113">Para obtener el punto de entrada, llame a la [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) método y especifique "CoEEShutDownCOM".</span><span class="sxs-lookup"><span data-stu-id="11824-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11824-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11824-114">Requirements</span></span>  
 <span data-ttu-id="11824-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11824-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11824-116">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="11824-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11824-117">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11824-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="11824-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11824-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11824-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="11824-119">See also</span></span>

- [<span data-ttu-id="11824-120">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="11824-120">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
