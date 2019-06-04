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
ms.openlocfilehash: 0d2b82bc056acd2e620461081b5f8c9d45fc152c
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490646"
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="7dbd2-102">CoEEShutDownCOM (Función)</span><span class="sxs-lookup"><span data-stu-id="7dbd2-102">CoEEShutDownCOM Function</span></span>
<span data-ttu-id="7dbd2-103">Obliga a common language runtime (CLR) para liberar todos los punteros de interfaz que tiene en los contenedores RCW (RCW).</span><span class="sxs-lookup"><span data-stu-id="7dbd2-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="7dbd2-104">Esto tiene el efecto de liberar todas las cachés RCW.</span><span class="sxs-lookup"><span data-stu-id="7dbd2-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="7dbd2-105">Esta función global está en desuso en .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="7dbd2-105">This global function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="7dbd2-106">En su lugar, use el punto de entrada para un tiempo de ejecución específico.</span><span class="sxs-lookup"><span data-stu-id="7dbd2-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7dbd2-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7dbd2-107">Syntax</span></span>  
  
```  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="7dbd2-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="7dbd2-108">Remarks</span></span>  
 <span data-ttu-id="7dbd2-109">El `CoEEShutDownCOM` función primero libera todos los RCW en todos los contextos y en todas las memorias caché y, a continuación, quita cualquier notificación de anulación existente en el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="7dbd2-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="7dbd2-110">Se produce ninguna descarga del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="7dbd2-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
>  <span data-ttu-id="7dbd2-111">Esta función afecta a todos los runtimes que se cargan en el proceso.</span><span class="sxs-lookup"><span data-stu-id="7dbd2-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="7dbd2-112">A partir de .NET Framework 4, llame al punto de entrada para esta función en el tiempo de ejecución específico que desea aplicar.</span><span class="sxs-lookup"><span data-stu-id="7dbd2-112">Beginning with the .NET Framework 4, call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="7dbd2-113">Para obtener el punto de entrada, llame a la [ICLRRuntimeInfo](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) método y especifique "CoEEShutDownCOM".</span><span class="sxs-lookup"><span data-stu-id="7dbd2-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7dbd2-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7dbd2-114">Requirements</span></span>  
 <span data-ttu-id="7dbd2-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7dbd2-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7dbd2-116">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="7dbd2-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7dbd2-117">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7dbd2-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7dbd2-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7dbd2-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7dbd2-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="7dbd2-119">See also</span></span>

- [<span data-ttu-id="7dbd2-120">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="7dbd2-120">Metadata Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
