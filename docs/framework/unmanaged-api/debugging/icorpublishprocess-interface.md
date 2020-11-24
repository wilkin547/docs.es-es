---
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
ms.openlocfilehash: 8ee59e9d416d1c53312e4fccb6953f20b03b29b3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95693099"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="80cf9-102">ICorPublishProcess (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="80cf9-102">ICorPublishProcess Interface</span></span>

<span data-ttu-id="80cf9-103">Proporciona métodos que tienen acceso a la información que se va a mostrar sobre un proceso.</span><span class="sxs-lookup"><span data-stu-id="80cf9-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="80cf9-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="80cf9-104">Methods</span></span>  
  
|<span data-ttu-id="80cf9-105">Método</span><span class="sxs-lookup"><span data-stu-id="80cf9-105">Method</span></span>|<span data-ttu-id="80cf9-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="80cf9-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="80cf9-107">Método EnumAppDomains</span><span class="sxs-lookup"><span data-stu-id="80cf9-107">EnumAppDomains Method</span></span>](icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="80cf9-108">Obtiene una instancia de [ICorPublishAppDomainEnum (](icorpublishappdomainenum-interface.md) que contiene los dominios de aplicación en el proceso al que hace referencia este `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="80cf9-108">Gets an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="80cf9-109">GetDisplayName (Método)</span><span class="sxs-lookup"><span data-stu-id="80cf9-109">GetDisplayName Method</span></span>](icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="80cf9-110">Obtiene la ruta de acceso completa del archivo ejecutable para el proceso al que hace referencia este `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="80cf9-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="80cf9-111">Método GetProcessID</span><span class="sxs-lookup"><span data-stu-id="80cf9-111">GetProcessID Method</span></span>](icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="80cf9-112">Obtiene el identificador del sistema operativo para el proceso al que hace referencia este `ICorPublishProcess` .</span><span class="sxs-lookup"><span data-stu-id="80cf9-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="80cf9-113">Método IsManaged</span><span class="sxs-lookup"><span data-stu-id="80cf9-113">IsManaged Method</span></span>](icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="80cf9-114">Obtiene un valor que indica si se sabe que el proceso al que hace referencia esto `ICorPublishProcess` está ejecutando código administrado.</span><span class="sxs-lookup"><span data-stu-id="80cf9-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="80cf9-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="80cf9-115">Requirements</span></span>  

 <span data-ttu-id="80cf9-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="80cf9-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="80cf9-117">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="80cf9-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="80cf9-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="80cf9-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="80cf9-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="80cf9-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="80cf9-120">Consulte también</span><span class="sxs-lookup"><span data-stu-id="80cf9-120">See also</span></span>

- [<span data-ttu-id="80cf9-121">Interfaces para depuración</span><span class="sxs-lookup"><span data-stu-id="80cf9-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="80cf9-122">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="80cf9-122">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
