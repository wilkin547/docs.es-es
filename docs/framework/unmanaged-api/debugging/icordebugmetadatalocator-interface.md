---
description: 'Más información acerca de: interfaz ICorDebugMetaDataLocator ('
title: ICorDebugMetaDataLocator (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugMetaDataLocator
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator
helpviewer_keywords:
- ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: 287f5ecd-863f-4090-a615-077859f0257b
topic_type:
- apiref
ms.openlocfilehash: 7b87527d4d0b98fc97631fb47184665daaf39edb
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790833"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="7ce16-103">ICorDebugMetaDataLocator (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7ce16-103">ICorDebugMetaDataLocator Interface</span></span>

<span data-ttu-id="7ce16-104">Proporciona información de metadatos al depurador.</span><span class="sxs-lookup"><span data-stu-id="7ce16-104">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7ce16-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="7ce16-105">Methods</span></span>  
  
|<span data-ttu-id="7ce16-106">Método</span><span class="sxs-lookup"><span data-stu-id="7ce16-106">Method</span></span>|<span data-ttu-id="7ce16-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="7ce16-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="7ce16-108">Método GetMetaData</span><span class="sxs-lookup"><span data-stu-id="7ce16-108">GetMetaData Method</span></span>](icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="7ce16-109">Pide al depurador que devuelva la ruta de acceso completa a un módulo cuyos metadatos se necesitan para completar una operación solicitada por el depurador.</span><span class="sxs-lookup"><span data-stu-id="7ce16-109">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="7ce16-110">Observaciones</span><span class="sxs-lookup"><span data-stu-id="7ce16-110">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="7ce16-111">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="7ce16-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="7ce16-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7ce16-112">Requirements</span></span>  

 <span data-ttu-id="7ce16-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7ce16-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ce16-114">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="7ce16-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="7ce16-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="7ce16-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="7ce16-116">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7ce16-116">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7ce16-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="7ce16-117">See also</span></span>

- [<span data-ttu-id="7ce16-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="7ce16-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="7ce16-119">Depuración</span><span class="sxs-lookup"><span data-stu-id="7ce16-119">Debugging</span></span>](index.md)
