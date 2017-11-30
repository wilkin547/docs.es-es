---
title: CorpubPublish (coclase)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorpubPublish Coclass
api_location: mscoree.dll
api_type: COM
f1_keywords: CorpubPublish
helpviewer_keywords: CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3c1565c9321e64536139e02b239fbeb4247a58a3
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="65eb0-102">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="65eb0-102">CorpubPublish Coclass</span></span>
<span data-ttu-id="65eb0-103">Proporciona interfaces para publicar información acerca de procesos y dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="65eb0-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65eb0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="65eb0-104">Syntax</span></span>  
  
```  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="65eb0-105">Interfaces</span><span class="sxs-lookup"><span data-stu-id="65eb0-105">Interfaces</span></span>  
  
|<span data-ttu-id="65eb0-106">Interfaz</span><span class="sxs-lookup"><span data-stu-id="65eb0-106">Interface</span></span>|<span data-ttu-id="65eb0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="65eb0-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="65eb0-108">ICorPublish (interfaz)</span><span class="sxs-lookup"><span data-stu-id="65eb0-108">ICorPublish Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublish-interface.md)|<span data-ttu-id="65eb0-109">Proporciona métodos para publicar información sobre los procesos y los dominios de aplicación en esos procesos.</span><span class="sxs-lookup"><span data-stu-id="65eb0-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="65eb0-110">ICorPublishAppDomain (interfaz)</span><span class="sxs-lookup"><span data-stu-id="65eb0-110">ICorPublishAppDomain Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomain-interface.md)|<span data-ttu-id="65eb0-111">Representa y proporciona información sobre un dominio de aplicación en un proceso.</span><span class="sxs-lookup"><span data-stu-id="65eb0-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="65eb0-112">ICorPublishAppDomainEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="65eb0-112">ICorPublishAppDomainEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishappdomainenum-interface.md)|<span data-ttu-id="65eb0-113">Proporciona métodos que atraviesan una colección de dominios de aplicación que actualmente existen dentro de un proceso.</span><span class="sxs-lookup"><span data-stu-id="65eb0-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="65eb0-114">ICorPublishProcess (interfaz)</span><span class="sxs-lookup"><span data-stu-id="65eb0-114">ICorPublishProcess Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocess-interface.md)|<span data-ttu-id="65eb0-115">Representa un proceso que se ejecuta en un equipo.</span><span class="sxs-lookup"><span data-stu-id="65eb0-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="65eb0-116">ICorPublishProcessEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="65eb0-116">ICorPublishProcessEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icorpublishprocessenum-interface.md)|<span data-ttu-id="65eb0-117">Proporciona métodos que atraviesan una colección de procesos que se ejecutan en un equipo.</span><span class="sxs-lookup"><span data-stu-id="65eb0-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="65eb0-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="65eb0-118">Remarks</span></span>  
 <span data-ttu-id="65eb0-119">Un escenario de publicación típico implica un programador que desea depurar código administrado que se ejecuta en un equipo dentro de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="65eb0-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="65eb0-120">El entorno de hospedaje puede ejecutarse más de un dominio de aplicación dentro de un proceso.</span><span class="sxs-lookup"><span data-stu-id="65eb0-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="65eb0-121">El desarrollador también desean usar una interfaz gráfica de usuario o algún otro medio para enumerar todos los procesos que se ejecutan en el equipo y elegir un proceso específico.</span><span class="sxs-lookup"><span data-stu-id="65eb0-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="65eb0-122">La lista debe incluir todos los dominios de aplicación dentro de los procesos que ejecutan código administrado.</span><span class="sxs-lookup"><span data-stu-id="65eb0-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="65eb0-123">El programador, a continuación, puede identificar el dominio de aplicación concreto y asociar a un depurador a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="65eb0-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="65eb0-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="65eb0-124">Requirements</span></span>  
 <span data-ttu-id="65eb0-125">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="65eb0-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="65eb0-126">**Encabezado:** Cordebug.idl</span><span class="sxs-lookup"><span data-stu-id="65eb0-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="65eb0-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="65eb0-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="65eb0-128">**Versiones de .NET framework:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="65eb0-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="65eb0-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="65eb0-129">See Also</span></span>  
 [<span data-ttu-id="65eb0-130">Depuración</span><span class="sxs-lookup"><span data-stu-id="65eb0-130">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
