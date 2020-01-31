---
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
ms.openlocfilehash: 24d245bbb0f9ac86e321491e0af3b66b1e011baa
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789218"
---
# <a name="corpubpublish-coclass"></a><span data-ttu-id="06422-102">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="06422-102">CorpubPublish Coclass</span></span>
<span data-ttu-id="06422-103">Proporciona interfaces para publicar información acerca de procesos y dominios de aplicación.</span><span class="sxs-lookup"><span data-stu-id="06422-103">Provides interfaces for publishing information about application domains and processes.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06422-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="06422-104">Syntax</span></span>  
  
```cpp  
coclass CorpubPublish {  
    [default] interface ICorPublish;  
    interface           ICorPublishProcess;  
    interface           ICorPublishAppDomain;  
    interface           ICorPublishProcessEnum;  
    interface           ICorPublishAppDomainEnum;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="06422-105">Interfaces</span><span class="sxs-lookup"><span data-stu-id="06422-105">Interfaces</span></span>  
  
|<span data-ttu-id="06422-106">Interfaz</span><span class="sxs-lookup"><span data-stu-id="06422-106">Interface</span></span>|<span data-ttu-id="06422-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="06422-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="06422-108">ICorPublish (interfaz)</span><span class="sxs-lookup"><span data-stu-id="06422-108">ICorPublish Interface</span></span>](icorpublish-interface.md)|<span data-ttu-id="06422-109">Proporciona métodos para publicar información sobre los procesos y los dominios de aplicación en esos procesos.</span><span class="sxs-lookup"><span data-stu-id="06422-109">Provides methods for publishing information about processes and the application domains in those processes.</span></span>|  
|[<span data-ttu-id="06422-110">ICorPublishAppDomain (interfaz)</span><span class="sxs-lookup"><span data-stu-id="06422-110">ICorPublishAppDomain Interface</span></span>](icorpublishappdomain-interface.md)|<span data-ttu-id="06422-111">Representa y proporciona información sobre un dominio de aplicación en un proceso.</span><span class="sxs-lookup"><span data-stu-id="06422-111">Represents, and provides information about, an application domain in a process.</span></span>|  
|[<span data-ttu-id="06422-112">ICorPublishAppDomainEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="06422-112">ICorPublishAppDomainEnum Interface</span></span>](icorpublishappdomainenum-interface.md)|<span data-ttu-id="06422-113">Proporciona métodos que atraviesan una colección de dominios de aplicación que existen actualmente dentro de un proceso.</span><span class="sxs-lookup"><span data-stu-id="06422-113">Provides methods that traverse a collection of application domains that currently exist within a process.</span></span>|  
|[<span data-ttu-id="06422-114">ICorPublishProcess (interfaz)</span><span class="sxs-lookup"><span data-stu-id="06422-114">ICorPublishProcess Interface</span></span>](icorpublishprocess-interface.md)|<span data-ttu-id="06422-115">Representa un proceso que se está ejecutando en un equipo.</span><span class="sxs-lookup"><span data-stu-id="06422-115">Represents a process that is running on a computer.</span></span>|  
|[<span data-ttu-id="06422-116">ICorPublishProcessEnum (interfaz)</span><span class="sxs-lookup"><span data-stu-id="06422-116">ICorPublishProcessEnum Interface</span></span>](icorpublishprocessenum-interface.md)|<span data-ttu-id="06422-117">Proporciona métodos que atraviesan una colección de procesos que se ejecutan en un equipo.</span><span class="sxs-lookup"><span data-stu-id="06422-117">Provides methods that traverse a collection of processes that are running on a computer.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="06422-118">Notas</span><span class="sxs-lookup"><span data-stu-id="06422-118">Remarks</span></span>  
 <span data-ttu-id="06422-119">Un escenario de publicación típico implica a un desarrollador que desea depurar el código administrado que se ejecuta en un equipo dentro de un dominio de aplicación.</span><span class="sxs-lookup"><span data-stu-id="06422-119">A typical publishing scenario involves a developer who wants to debug managed code that is running on a computer within an application domain.</span></span> <span data-ttu-id="06422-120">Es posible que el entorno de hospedaje ejecute más de un dominio de aplicación dentro de un proceso.</span><span class="sxs-lookup"><span data-stu-id="06422-120">The hosting environment may be running more than one application domain within a process.</span></span> <span data-ttu-id="06422-121">El desarrollador desea usar una interfaz gráfica de usuario u otros medios para enumerar todos los procesos que se ejecutan en el equipo y elegir un proceso específico.</span><span class="sxs-lookup"><span data-stu-id="06422-121">The developer would like to use a graphical user interface or some other means to list all of the processes that are running on the computer, and pick a specific process.</span></span> <span data-ttu-id="06422-122">La lista debe incluir todos los dominios de aplicación dentro de los procesos que ejecutan código administrado.</span><span class="sxs-lookup"><span data-stu-id="06422-122">The listing should include all of the application domains within processes that are running managed code.</span></span> <span data-ttu-id="06422-123">A continuación, el desarrollador puede identificar el dominio de aplicación específico y asociar un depurador a ese dominio.</span><span class="sxs-lookup"><span data-stu-id="06422-123">The developer can then identify the specific application domain and attach a debugger to that domain.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06422-124">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="06422-124">Requirements</span></span>  
 <span data-ttu-id="06422-125">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="06422-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06422-126">**Encabezado:** CorPub. idl</span><span class="sxs-lookup"><span data-stu-id="06422-126">**Header:** CorPub.idl</span></span>  
  
 <span data-ttu-id="06422-127">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="06422-127">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="06422-128">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06422-128">**.NET Framework Versions:**  [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06422-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="06422-129">See also</span></span>

- [<span data-ttu-id="06422-130">Depuración</span><span class="sxs-lookup"><span data-stu-id="06422-130">Debugging</span></span>](index.md)
