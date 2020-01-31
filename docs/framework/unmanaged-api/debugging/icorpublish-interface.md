---
title: ICorPublish (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorPublish
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublish
helpviewer_keywords:
- ICorPublish interface [.NET Framework debugging]
ms.assetid: 87c4fcb2-7703-4a2e-afb6-42973381b960
topic_type:
- apiref
ms.openlocfilehash: c4a24d879ebd9e8813ea0ac4597818569f4ae6fa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790721"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="c713f-102">ICorPublish (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c713f-102">ICorPublish Interface</span></span>
<span data-ttu-id="c713f-103">Actúa como la interfaz general para publicar información sobre procesos e información sobre los dominios de aplicación en esos procesos.</span><span class="sxs-lookup"><span data-stu-id="c713f-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c713f-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c713f-104">Methods</span></span>  
  
|<span data-ttu-id="c713f-105">Método</span><span class="sxs-lookup"><span data-stu-id="c713f-105">Method</span></span>|<span data-ttu-id="c713f-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c713f-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c713f-107">EnumProcesses (método)</span><span class="sxs-lookup"><span data-stu-id="c713f-107">EnumProcesses Method</span></span>](icorpublish-enumprocesses-method.md)|<span data-ttu-id="c713f-108">Obtiene una instancia de [ICorPublishProcessEnum (](icorpublishprocessenum-interface.md) que contiene los procesos administrados que se ejecutan en este equipo.</span><span class="sxs-lookup"><span data-stu-id="c713f-108">Gets an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="c713f-109">GetProcess (método)</span><span class="sxs-lookup"><span data-stu-id="c713f-109">GetProcess Method</span></span>](icorpublish-getprocess-method.md)|<span data-ttu-id="c713f-110">Obtiene una instancia de [ICorPublishProcess](icorpublishprocess-interface.md) que representa el proceso con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="c713f-110">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c713f-111">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="c713f-111">Requirements</span></span>  
 <span data-ttu-id="c713f-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c713f-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c713f-113">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="c713f-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="c713f-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="c713f-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="c713f-115">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c713f-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c713f-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="c713f-116">See also</span></span>

- [<span data-ttu-id="c713f-117">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="c713f-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="c713f-118">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="c713f-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
