---
description: 'Más información acerca de: interfaz Iapartmentcallback ('
title: IApartmentCallback (Interfaz)
ms.date: 03/30/2017
api_name:
- IApartmentCallback
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IApartmentCallback
helpviewer_keywords:
- IApartmentCallback interface [.NET Framework hosting]
ms.assetid: 57c33c58-bf0b-4533-b569-e6a682d02cba
topic_type:
- apiref
ms.openlocfilehash: ddf99b1d926bd2d9765b936143785a975ea378a7
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785147"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="60201-103">IApartmentCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="60201-103">IApartmentCallback Interface</span></span>

<span data-ttu-id="60201-104">Proporciona métodos para crear devoluciones de llamada dentro de un contenedor.</span><span class="sxs-lookup"><span data-stu-id="60201-104">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="60201-105">Un *Apartamento* es un contenedor lógico dentro de un proceso para objetos que comparten los mismos requisitos de acceso de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="60201-105">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="60201-106">Métodos</span><span class="sxs-lookup"><span data-stu-id="60201-106">Methods</span></span>  
  
|<span data-ttu-id="60201-107">Método</span><span class="sxs-lookup"><span data-stu-id="60201-107">Method</span></span>|<span data-ttu-id="60201-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="60201-108">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="60201-109">Método DoCallback</span><span class="sxs-lookup"><span data-stu-id="60201-109">DoCallback Method</span></span>](iapartmentcallback-docallback-method.md)|<span data-ttu-id="60201-110">Ejecuta la función especificada dentro de un contenedor.</span><span class="sxs-lookup"><span data-stu-id="60201-110">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="60201-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="60201-111">Requirements</span></span>  

 <span data-ttu-id="60201-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="60201-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="60201-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="60201-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="60201-114">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="60201-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="60201-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="60201-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="60201-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="60201-116">See also</span></span>

- [<span data-ttu-id="60201-117">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="60201-117">Hosting Interfaces</span></span>](hosting-interfaces.md)
