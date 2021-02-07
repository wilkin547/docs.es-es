---
description: 'Más información acerca de: ICorPublish (interfaz)'
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
ms.openlocfilehash: 0cec1d3407246989c6b916ca0760e6f556566ce6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99721832"
---
# <a name="icorpublish-interface"></a><span data-ttu-id="f1675-103">ICorPublish (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f1675-103">ICorPublish Interface</span></span>

<span data-ttu-id="f1675-104">Actúa como la interfaz general para publicar información sobre procesos e información sobre los dominios de aplicación en esos procesos.</span><span class="sxs-lookup"><span data-stu-id="f1675-104">Serves as the general interface for publishing information about processes and information about the application domains in those processes.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f1675-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="f1675-105">Methods</span></span>  
  
|<span data-ttu-id="f1675-106">Método</span><span class="sxs-lookup"><span data-stu-id="f1675-106">Method</span></span>|<span data-ttu-id="f1675-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f1675-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="f1675-108">Método EnumProcesses</span><span class="sxs-lookup"><span data-stu-id="f1675-108">EnumProcesses Method</span></span>](icorpublish-enumprocesses-method.md)|<span data-ttu-id="f1675-109">Obtiene una instancia de [ICorPublishProcessEnum (](icorpublishprocessenum-interface.md) que contiene los procesos administrados que se ejecutan en este equipo.</span><span class="sxs-lookup"><span data-stu-id="f1675-109">Gets an [ICorPublishProcessEnum](icorpublishprocessenum-interface.md) instance that contains the managed processes running on this computer.</span></span>|  
|[<span data-ttu-id="f1675-110">Método GetProcess</span><span class="sxs-lookup"><span data-stu-id="f1675-110">GetProcess Method</span></span>](icorpublish-getprocess-method.md)|<span data-ttu-id="f1675-111">Obtiene una instancia de [ICorPublishProcess](icorpublishprocess-interface.md) que representa el proceso con el identificador especificado.</span><span class="sxs-lookup"><span data-stu-id="f1675-111">Gets an [ICorPublishProcess](icorpublishprocess-interface.md) instance that represents the process with the specified identifier.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f1675-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f1675-112">Requirements</span></span>  

 <span data-ttu-id="f1675-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f1675-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f1675-114">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="f1675-114">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="f1675-115">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f1675-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f1675-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f1675-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f1675-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="f1675-117">See also</span></span>

- [<span data-ttu-id="f1675-118">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="f1675-118">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="f1675-119">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="f1675-119">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
