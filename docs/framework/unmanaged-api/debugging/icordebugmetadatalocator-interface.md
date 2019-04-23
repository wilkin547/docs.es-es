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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4e9b9221aa2f5e048a94c225660ba2ac9214549c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59108840"
---
# <a name="icordebugmetadatalocator-interface"></a><span data-ttu-id="a219a-102">ICorDebugMetaDataLocator (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a219a-102">ICorDebugMetaDataLocator Interface</span></span>
<span data-ttu-id="a219a-103">Proporciona información de metadatos al depurador.</span><span class="sxs-lookup"><span data-stu-id="a219a-103">Provides metadata information to the debugger.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a219a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a219a-104">Methods</span></span>  
  
|<span data-ttu-id="a219a-105">Método</span><span class="sxs-lookup"><span data-stu-id="a219a-105">Method</span></span>|<span data-ttu-id="a219a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a219a-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a219a-107">GetMetaData (método)</span><span class="sxs-lookup"><span data-stu-id="a219a-107">GetMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmetadatalocator-getmetadata-method.md)|<span data-ttu-id="a219a-108">Pide al depurador que devuelva la ruta de acceso completa a un módulo cuyos metadatos se necesitan para completar una operación solicitada por el depurador.</span><span class="sxs-lookup"><span data-stu-id="a219a-108">Asks the debugger to return the full path to a module whose metadata is needed to complete an operation the debugger requested.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a219a-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a219a-109">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="a219a-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="a219a-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a219a-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a219a-111">Requirements</span></span>  
 <span data-ttu-id="a219a-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a219a-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a219a-113">**Encabezado**: CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a219a-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a219a-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a219a-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a219a-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a219a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a219a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="a219a-116">See also</span></span>

- [<span data-ttu-id="a219a-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="a219a-117">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [<span data-ttu-id="a219a-118">Depuración</span><span class="sxs-lookup"><span data-stu-id="a219a-118">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
