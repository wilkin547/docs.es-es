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
ms.openlocfilehash: 3ae48df9e66890161c1aef944d37b0a279939d56
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76790546"
---
# <a name="icorpublishprocess-interface"></a><span data-ttu-id="392b6-102">ICorPublishProcess (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="392b6-102">ICorPublishProcess Interface</span></span>
<span data-ttu-id="392b6-103">Proporciona métodos que tienen acceso a la información que se va a mostrar sobre un proceso.</span><span class="sxs-lookup"><span data-stu-id="392b6-103">Provides methods that access information to be displayed about a process.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="392b6-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="392b6-104">Methods</span></span>  
  
|<span data-ttu-id="392b6-105">Método</span><span class="sxs-lookup"><span data-stu-id="392b6-105">Method</span></span>|<span data-ttu-id="392b6-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="392b6-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="392b6-107">EnumAppDomains (método)</span><span class="sxs-lookup"><span data-stu-id="392b6-107">EnumAppDomains Method</span></span>](icorpublishprocess-enumappdomains-method.md)|<span data-ttu-id="392b6-108">Obtiene una instancia de [ICorPublishAppDomainEnum (](icorpublishappdomainenum-interface.md) que contiene los dominios de aplicación en el proceso al que hace referencia este `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="392b6-108">Gets an [ICorPublishAppDomainEnum](icorpublishappdomainenum-interface.md) instance that contains the application domains in the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="392b6-109">GetDisplayName (método)</span><span class="sxs-lookup"><span data-stu-id="392b6-109">GetDisplayName Method</span></span>](icorpublishprocess-getdisplayname-method.md)|<span data-ttu-id="392b6-110">Obtiene la ruta de acceso completa del archivo ejecutable para el proceso al que hace referencia este `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="392b6-110">Gets the full path of the executable for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="392b6-111">GetProcessID (método)</span><span class="sxs-lookup"><span data-stu-id="392b6-111">GetProcessID Method</span></span>](icorpublishprocess-getprocessid-method.md)|<span data-ttu-id="392b6-112">Obtiene el identificador del sistema operativo para el proceso al que hace referencia este `ICorPublishProcess`.</span><span class="sxs-lookup"><span data-stu-id="392b6-112">Gets the operating system identifier for the process referenced by this `ICorPublishProcess`.</span></span>|  
|[<span data-ttu-id="392b6-113">IsManaged (método)</span><span class="sxs-lookup"><span data-stu-id="392b6-113">IsManaged Method</span></span>](icorpublishprocess-ismanaged-method.md)|<span data-ttu-id="392b6-114">Obtiene un valor que indica si se sabe que el proceso al que hace referencia esta `ICorPublishProcess` está ejecutando código administrado.</span><span class="sxs-lookup"><span data-stu-id="392b6-114">Gets a value that indicates whether the process referenced by this `ICorPublishProcess` is known to be running managed code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="392b6-115">Requisitos de</span><span class="sxs-lookup"><span data-stu-id="392b6-115">Requirements</span></span>  
 <span data-ttu-id="392b6-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="392b6-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="392b6-117">**Encabezado:** CorPub. idl, CorPub. h</span><span class="sxs-lookup"><span data-stu-id="392b6-117">**Header:** CorPub.idl, CorPub.h</span></span>  
  
 <span data-ttu-id="392b6-118">**Biblioteca:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="392b6-118">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="392b6-119">**.NET Framework versiones:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="392b6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="392b6-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="392b6-120">See also</span></span>

- [<span data-ttu-id="392b6-121">Interfaces de depuración</span><span class="sxs-lookup"><span data-stu-id="392b6-121">Debugging Interfaces</span></span>](debugging-interfaces.md)
- [<span data-ttu-id="392b6-122">CorpubPublish (coclase)</span><span class="sxs-lookup"><span data-stu-id="392b6-122">CorpubPublish Coclass</span></span>](corpubpublish-coclass.md)
