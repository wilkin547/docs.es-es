---
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
ms.openlocfilehash: dbf5c751e84dfd9bf0549e8ce79d07a90fb4a3b2
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710394"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="2fe6b-102">ICorDebugMetaDataLocator (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2fe6b-102">ICorDebugMetaDataLocator Interface</span></span>

<span data-ttu-id="2fe6b-103">Proporciona información de metadatos al depurador.</span><span class="sxs-lookup"><span data-stu-id="2fe6b-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2fe6b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="2fe6b-104">Methods</span></span>  
  
|<span data-ttu-id="2fe6b-105">Método</span><span class="sxs-lookup"><span data-stu-id="2fe6b-105">Method</span></span>|<span data-ttu-id="2fe6b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="2fe6b-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2fe6b-107">Método GetMetaData</span><span class="sxs-lookup"><span data-stu-id="2fe6b-107">GetMetaData Method</span></span>](icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="2fe6b-108">Pide al depurador que devuelva la ruta de acceso completa a un módulo cuyos metadatos se necesitan para completar una operación solicitada por el depurador.</span><span class="sxs-lookup"><span data-stu-id="2fe6b-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2fe6b-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2fe6b-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="2fe6b-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="2fe6b-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2fe6b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2fe6b-111">Requirements</span></span>  

 <span data-ttu-id="2fe6b-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2fe6b-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2fe6b-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="2fe6b-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="2fe6b-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="2fe6b-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="2fe6b-115">**.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2fe6b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2fe6b-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2fe6b-116">See also</span></span>

- [<span data-ttu-id="2fe6b-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="2fe6b-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="2fe6b-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="2fe6b-118">Debugging</span></span>](index.md)
