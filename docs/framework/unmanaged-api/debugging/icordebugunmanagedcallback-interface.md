---
title: ICorDebugUnmanagedCallback (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorDebugUnmanagedCallback
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugUnmanagedCallback
helpviewer_keywords:
- ICorDebugUnmanagedCallback interface [.NET Framework debugging]
ms.assetid: bc71cbca-7d73-40e5-84dd-2109fade3c2a
topic_type:
- apiref
ms.openlocfilehash: dd5baa282d15d121b62b4dc4dd41bcf9ff393570
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395880"
---
# <a name="icordebugunmanagedcallback-interface"></a><span data-ttu-id="d2647-102">ICorDebugUnmanagedCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d2647-102">ICorDebugUnmanagedCallback Interface</span></span>
<span data-ttu-id="d2647-103">Proporciona la notificación de eventos nativos que no están directamente relacionados con el Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d2647-103">Provides notification of native events that are not directly related to the common language runtime (CLR).</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d2647-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d2647-104">Methods</span></span>  
  
|<span data-ttu-id="d2647-105">Método</span><span class="sxs-lookup"><span data-stu-id="d2647-105">Method</span></span>|<span data-ttu-id="d2647-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d2647-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d2647-107">Método DebugEvent</span><span class="sxs-lookup"><span data-stu-id="d2647-107">DebugEvent Method</span></span>](icordebugunmanagedcallback-debugevent-method.md)|<span data-ttu-id="d2647-108">Notifica al depurador que se ha desencadenado un evento nativo.</span><span class="sxs-lookup"><span data-stu-id="d2647-108">Notifies the debugger that a native event has been fired.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d2647-109">Comentarios</span><span class="sxs-lookup"><span data-stu-id="d2647-109">Remarks</span></span>  
  
> [!NOTE]
> <span data-ttu-id="d2647-110">Esta interfaz no admite que se la llame de forma remota, ya sea entre procesos o entre equipos.</span><span class="sxs-lookup"><span data-stu-id="d2647-110">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d2647-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d2647-111">Requirements</span></span>  
 <span data-ttu-id="d2647-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d2647-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d2647-113">**Encabezado:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d2647-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d2647-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d2647-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d2647-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d2647-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d2647-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d2647-116">See also</span></span>

- [<span data-ttu-id="d2647-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="d2647-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
