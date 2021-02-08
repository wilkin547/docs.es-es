---
description: 'Más información sobre: interfaz ICorPublishProcess'
title: ICorPublishProcess (Interfaz)
ms.date: 03/30/2017
api_name:
- ICorPublishProcess
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorPublishProcess
helpviewer_keywords:
- ICorPublishProcess interface [.NET Framework debugging]
ms.assetid: 6d1dc41b-8aa2-4889-bb00-1cbccc00c123
topic_type:
- apiref
ms.openlocfilehash: 8dbc619d33c2c9b625dde852948dff00b5be926e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800882"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="3c8c9-103">ICorPublishProcess (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3c8c9-103">ICorPublishProcess Interface</span></span>

<span data-ttu-id="3c8c9-104">Proporciona métodos que tienen acceso a la información que se va a mostrar sobre un proceso.</span><span class="sxs-lookup"><span data-stu-id="3c8c9-104">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="3c8c9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="3c8c9-105">Methods</span></span>  
  
|<span data-ttu-id="3c8c9-106">Método</span><span class="sxs-lookup"><span data-stu-id="3c8c9-106">Method</span></span>|<span data-ttu-id="3c8c9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="3c8c9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="3c8c9-108">Método EnumAppDomains</span><span class="sxs-lookup"><span data-stu-id="3c8c9-108">EnumAppDomains Method</span></span>](icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="3c8c9-109">Obtiene una instancia de [ICorPublishAppDomainEnum (](icorpublishappdomainenum-interface.md) que contiene los dominios de aplicación en el proceso al que hace referencia este `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="3c8c9-109">Gets an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="3c8c9-110">Método GetDisplayName</span><span class="sxs-lookup"><span data-stu-id="3c8c9-110">GetDisplayName Method</span></span>](icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="3c8c9-111">Obtiene la ruta de acceso completa del archivo ejecutable para el proceso al que hace referencia este `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="3c8c9-111">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="3c8c9-112">Método GetProcessID</span><span class="sxs-lookup"><span data-stu-id="3c8c9-112">GetProcessID Method</span></span>](icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="3c8c9-113">Obtiene el identificador del sistema operativo para el proceso al que hace referencia este `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="3c8c9-113">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="3c8c9-114">Método IsManaged</span><span class="sxs-lookup"><span data-stu-id="3c8c9-114">IsManaged Method</span></span>](icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="3c8c9-115">Obtiene un valor que indica si se sabe que el proceso al que hace referencia esto `ICorPublishProcess` está ejecutando código administrado.</span><span class="sxs-lookup"><span data-stu-id="3c8c9-115">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="3c8c9-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3c8c9-116">Requirements</span></span>  

 <span data-ttu-id="3c8c9-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3c8c9-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3c8c9-118">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="3c8c9-118">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="3c8c9-119">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="3c8c9-119">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="3c8c9-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3c8c9-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3c8c9-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="3c8c9-121">See also</span></span>

- [<span data-ttu-id="3c8c9-122">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="3c8c9-122">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="3c8c9-123">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="3c8c9-123">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
