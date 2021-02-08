---
description: 'Más información acerca de: Coeeshutdowncom ((función)'
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
ms.openlocfilehash: 4f1ac8107c9a121ebf52ef21a5f2c9006880914f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799868"
---
# <a name="coeeshutdowncom-function"></a><span data-ttu-id="fe19e-103">CoEEShutDownCOM (Función)</span><span class="sxs-lookup"><span data-stu-id="fe19e-103">CoEEShutDownCOM Function</span></span>

<span data-ttu-id="fe19e-104">Obliga al Common Language Runtime (CLR) a liberar todos los punteros de interfaz que contiene dentro de contenedores RCW (Runtime Callable wrappers).</span><span class="sxs-lookup"><span data-stu-id="fe19e-104">Forces the common language runtime (CLR) to release all interface pointers it holds inside runtime callable wrappers (RCW).</span></span> <span data-ttu-id="fe19e-105">Esto tiene el efecto de liberar todas las memorias caché de RCW.</span><span class="sxs-lookup"><span data-stu-id="fe19e-105">This has the effect of releasing all RCW caches.</span></span> <span data-ttu-id="fe19e-106">Esta función global está en desuso en el .NET Framework 4.</span><span class="sxs-lookup"><span data-stu-id="fe19e-106">This global function is deprecated in the .NET Framework 4.</span></span> <span data-ttu-id="fe19e-107">En su lugar, use el punto de entrada para un tiempo de ejecución específico.</span><span class="sxs-lookup"><span data-stu-id="fe19e-107">Instead, use the entry point for a specific runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fe19e-108">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fe19e-108">Syntax</span></span>  
  
```cpp  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a><span data-ttu-id="fe19e-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="fe19e-109">Remarks</span></span>  

 <span data-ttu-id="fe19e-110">La `CoEEShutDownCOM` función libera primero todos los RCW en todos los contextos y en todas las cachés y, a continuación, quita cualquier notificación de desactivación existente en el programa de instalación.</span><span class="sxs-lookup"><span data-stu-id="fe19e-110">The `CoEEShutDownCOM` function first releases all the RCWs in all contexts and in all caches, and then removes any tear-down notification existing in setup.</span></span> <span data-ttu-id="fe19e-111">No se produce ninguna descarga del archivo DLL.</span><span class="sxs-lookup"><span data-stu-id="fe19e-111">No DLL unloading occurs.</span></span>  
  
> [!CAUTION]
> <span data-ttu-id="fe19e-112">Esta función afecta a todos los Runtimes que se cargan en el proceso.</span><span class="sxs-lookup"><span data-stu-id="fe19e-112">This function affects all runtimes that are loaded into the process.</span></span>  
  
 <span data-ttu-id="fe19e-113">A partir de la .NET Framework 4, llame al punto de entrada de esta función en el tiempo de ejecución específico que desee modificar.</span><span class="sxs-lookup"><span data-stu-id="fe19e-113">Beginning with the .NET Framework 4, call the entry point for this function on the specific runtime you want to affect.</span></span> <span data-ttu-id="fe19e-114">Para obtener el punto de entrada, llame al método [ICLRRuntimeInfo:: GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) y especifique "coeeshutdowncom (".</span><span class="sxs-lookup"><span data-stu-id="fe19e-114">To get the entry point, call the [ICLRRuntimeInfo::GetProcAddress](iclrruntimeinfo-getprocaddress-method.md) method and specify "CoEEShutDownCOM".</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fe19e-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fe19e-115">Requirements</span></span>  

 <span data-ttu-id="fe19e-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fe19e-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fe19e-117">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fe19e-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fe19e-118">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="fe19e-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fe19e-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fe19e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe19e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="fe19e-120">See also</span></span>

- [<span data-ttu-id="fe19e-121">Funciones estáticas globales para metadatos</span><span class="sxs-lookup"><span data-stu-id="fe19e-121">Metadata Global Static Functions</span></span>](../metadata/metadata-global-static-functions.md)
