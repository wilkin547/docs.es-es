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
ms.openlocfilehash: 774704698f92d546d6bafa61c65d18d083c65f89
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95716764"
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="57b8a-102">CoEEShutDownCOM (Función)</span><span class="sxs-lookup"><span data-stu-id="57b8a-102">CoEEShutDownCOM Function</span></span>

<span data-ttu-id="57b8a-103">Obliga al Common Language Runtime (CLR) a liberar todos los punteros de interfaz que contiene dentro de contenedores RCW (Runtime Callable wrappers).</span><span class="sxs-lookup"><span data-stu-id="57b8a-103">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="57b8a-104">Esto tiene el efecto de liberar todas las memorias caché de RCW.</span><span class="sxs-lookup"><span data-stu-id="57b8a-104">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="57b8a-105">Esta función global está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="57b8a-105">This global function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="57b8a-106">En su lugar, use el punto de entrada para un tiempo de ejecución específico.</span><span class="sxs-lookup"><span data-stu-id="57b8a-106">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="57b8a-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="57b8a-107">Syntax</span></span>  
  
```cpp  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="57b8a-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="57b8a-108">Remarks</span></span>  

 <span data-ttu-id="57b8a-109">La `CoEEShutDownCOM` función libera primero todos los RCW en todos los contextos y en todas las cachés y, a continuación, quita cualquier notificación de desactivación existente en el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="57b8a-109">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="57b8a-110">No se produce ninguna descarga del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="57b8a-110">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="57b8a-111">Esta función afecta a todos los Runtimes que se cargan en el proceso.</span><span class="sxs-lookup"><span data-stu-id="57b8a-111">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="57b8a-112">A partir de la .NET Framework 4, llame al punto de entrada de esta función en el tiempo de ejecución específico que desee modificar.</span><span class="sxs-lookup"><span data-stu-id="57b8a-112">Beginning with the .NET Framework 4, call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="57b8a-113">Para obtener el punto de entrada, llame al método [ICLRRuntimeInfo:: GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) y especifique "coeeshutdowncom (".</span><span class="sxs-lookup"><span data-stu-id="57b8a-113">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="57b8a-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="57b8a-114">Requirements</span></span>  

 <span data-ttu-id="57b8a-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="57b8a-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="57b8a-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="57b8a-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="57b8a-117">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="57b8a-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="57b8a-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="57b8a-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="57b8a-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="57b8a-119">See also</span></span>

- [<span data-ttu-id="57b8a-120">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="57b8a-120">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
