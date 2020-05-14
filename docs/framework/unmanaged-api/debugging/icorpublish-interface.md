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
ms.openlocfilehash: 1bd2f537cfa6a27c24ba91ea7caa29dc9e71a74e
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396323"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="db823-102">ICorPublish (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="db823-102">ICorPublish Interface</span></span>
<span data-ttu-id="db823-103">Actúa como la interfaz general para publicar información sobre procesos e información sobre los dominios de aplicación en esos procesos.</span><span class="sxs-lookup"><span data-stu-id="db823-103">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="db823-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="db823-104">Methods</span></span>  
  
|<span data-ttu-id="db823-105">Método</span><span class="sxs-lookup"><span data-stu-id="db823-105">Method</span></span>|<span data-ttu-id="db823-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="db823-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="db823-107">Método EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="db823-107">EnumProcesses Method</span></span>](icorpublish-enumprocesses-method.md)|<span data-ttu-id="db823-108">Obtiene una instancia de [ICorPublishProcessEnum (](icorpublishprocessenum-interface.md) que contiene los procesos administrados que se ejecutan en este equipo.</span><span class="sxs-lookup"><span data-stu-id="db823-108">Gets an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="db823-109">Método GetProcess</span><span class="sxs-lookup"><span data-stu-id="db823-109">GetProcess Method</span></span>](icorpublish-getprocess-method.md)|<span data-ttu-id="db823-110">Obtiene una instancia de [ICorPublishProcess](icorpublishprocess-interface.md) que representa el proceso con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="db823-110">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="db823-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="db823-111">Requirements</span></span>  
 <span data-ttu-id="db823-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="db823-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db823-113">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="db823-113">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="db823-114">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db823-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db823-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db823-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="db823-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="db823-116">See also</span></span>

- [<span data-ttu-id="db823-117">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="db823-117">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="db823-118">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="db823-118">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
