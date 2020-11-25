---
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
ms.openlocfilehash: 0f38314df766b74164bf5e98d9b2153d2dddbcc1
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95721743"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="24418-102">IApartmentCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="24418-102">IApartmentCallback Interface</span></span>

<span data-ttu-id="24418-103">Proporciona métodos para crear devoluciones de llamada dentro de un contenedor.</span><span class="sxs-lookup"><span data-stu-id="24418-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="24418-104">Un *Apartamento* es un contenedor lógico dentro de un proceso para objetos que comparten los mismos requisitos de acceso de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="24418-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="24418-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="24418-105">Methods</span></span>  
  
|<span data-ttu-id="24418-106">Método</span><span class="sxs-lookup"><span data-stu-id="24418-106">Method</span></span>|<span data-ttu-id="24418-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="24418-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="24418-108">Método DoCallback</span><span class="sxs-lookup"><span data-stu-id="24418-108">DoCallback Method</span></span>](iapartmentcallback-docallback-method.md)|<span data-ttu-id="24418-109">Ejecuta la función especificada dentro de un contenedor.</span><span class="sxs-lookup"><span data-stu-id="24418-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="24418-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="24418-110">Requirements</span></span>  

 <span data-ttu-id="24418-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="24418-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="24418-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="24418-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="24418-113">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="24418-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="24418-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="24418-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24418-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="24418-115">See also</span></span>

- [<span data-ttu-id="24418-116">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="24418-116">Hosting Interfaces</span></span>](hosting-interfaces.md)
