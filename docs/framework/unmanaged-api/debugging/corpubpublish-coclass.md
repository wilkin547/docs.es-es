---
description: 'Más información acerca de: coclase Corpubpublish ('
title: CorpubPublish (coclase)
ms.date: 03/30/2017
api_name:
- CorpubPublish Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorpubPublish
helpviewer_keywords:
- CorpubPublish coclass [.NET Framework debugging]
ms.assetid: 191015da-f54a-4bac-a28a-1de7ab3c3428
topic_type:
- apiref
ms.openlocfilehash: fdf4be6ff2d20391e989998cd0045ed27d602561
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661706"
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="44e0b-103">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="44e0b-103">CorpubPublish Coclass</span></span>

<span data-ttu-id="44e0b-104">Proporciona interfaces para publicar información acerca de procesos y dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="44e0b-104">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="44e0b-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="44e0b-105">Syntax</span></span>  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="44e0b-106">Interfaces</span><span class="sxs-lookup"><span data-stu-id="44e0b-106">Interfaces</span></span>  
  
|<span data-ttu-id="44e0b-107">Interfaz</span><span class="sxs-lookup"><span data-stu-id="44e0b-107">Interface</span></span>|<span data-ttu-id="44e0b-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="44e0b-108">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="44e0b-109">ICorPublish (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="44e0b-109">ICorPublish Interface</span></span>](icorpublish-interface.md)|<span data-ttu-id="44e0b-110">Proporciona métodos para publicar información sobre los procesos y los dominios de aplicación en esos procesos.</span><span class="sxs-lookup"><span data-stu-id="44e0b-110">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="44e0b-111">ICorPublishAppDomain (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="44e0b-111">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)|<span data-ttu-id="44e0b-112">Representa y proporciona información sobre un dominio de aplicación en un proceso.</span><span class="sxs-lookup"><span data-stu-id="44e0b-112">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="44e0b-113">ICorPublishAppDomainEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="44e0b-113">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)|<span data-ttu-id="44e0b-114">Proporciona métodos que atraviesan una colección de dominios de aplicación que existen actualmente dentro de un proceso.</span><span class="sxs-lookup"><span data-stu-id="44e0b-114">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="44e0b-115">ICorPublishProcess (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="44e0b-115">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)|<span data-ttu-id="44e0b-116">Representa un proceso que se está ejecutando en un equipo.</span><span class="sxs-lookup"><span data-stu-id="44e0b-116">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="44e0b-117">ICorPublishProcessEnum (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="44e0b-117">ICorPublishProcessEnum Interface</span></span>](icorpublishprocessenum-interface.md)|<span data-ttu-id="44e0b-118">Proporciona métodos que atraviesan una colección de procesos que se ejecutan en un equipo.</span><span class="sxs-lookup"><span data-stu-id="44e0b-118">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="44e0b-119">Observaciones</span><span class="sxs-lookup"><span data-stu-id="44e0b-119">Remarks</span></span>  

 <span data-ttu-id="44e0b-120">Un escenario de publicación típico implica a un desarrollador que desea depurar el código administrado que se ejecuta en un equipo dentro de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="44e0b-120">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="44e0b-121">Es posible que el entorno de hospedaje ejecute más de un dominio de aplicación dentro de un proceso.</span><span class="sxs-lookup"><span data-stu-id="44e0b-121">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="44e0b-122">El desarrollador desea usar una interfaz gráfica de usuario u otros medios para enumerar todos los procesos que se ejecutan en el equipo y elegir un proceso específico.</span><span class="sxs-lookup"><span data-stu-id="44e0b-122">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="44e0b-123">La lista debe incluir todos los dominios de aplicación dentro de los procesos que ejecutan código administrado.</span><span class="sxs-lookup"><span data-stu-id="44e0b-123">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="44e0b-124">A continuación, el desarrollador puede identificar el dominio de aplicación específico y asociar un depurador a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="44e0b-124">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="44e0b-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="44e0b-125">Requirements</span></span>  

 <span data-ttu-id="44e0b-126">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="44e0b-126">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="44e0b-127">**Encabezado:** CorPub. idl</span><span class="sxs-lookup"><span data-stu-id="44e0b-127">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="44e0b-128">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="44e0b-128">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="44e0b-129">**.NET Framework versiones:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="44e0b-129">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="44e0b-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="44e0b-130">See also</span></span>

- [<span data-ttu-id="44e0b-131">Depuración</span><span class="sxs-lookup"><span data-stu-id="44e0b-131">Debugging</span></span>](index.md)
