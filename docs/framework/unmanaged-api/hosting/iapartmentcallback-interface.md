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
ms.openlocfilehash: 4424509c16dd1d9f83db117ae7343fa03995297e
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73126911"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="d52a9-102">IApartmentCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d52a9-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="d52a9-103">Proporciona métodos para crear devoluciones de llamada dentro de un contenedor.</span><span class="sxs-lookup"><span data-stu-id="d52a9-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="d52a9-104">Un *Apartamento* es un contenedor lógico dentro de un proceso para objetos que comparten los mismos requisitos de acceso de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="d52a9-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d52a9-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="d52a9-105">Methods</span></span>  
  
|<span data-ttu-id="d52a9-106">Método</span><span class="sxs-lookup"><span data-stu-id="d52a9-106">Method</span></span>|<span data-ttu-id="d52a9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d52a9-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d52a9-108">DoCallback (método)</span><span class="sxs-lookup"><span data-stu-id="d52a9-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="d52a9-109">Ejecuta la función especificada dentro de un contenedor.</span><span class="sxs-lookup"><span data-stu-id="d52a9-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d52a9-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d52a9-110">Requirements</span></span>  
 <span data-ttu-id="d52a9-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d52a9-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d52a9-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d52a9-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d52a9-113">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d52a9-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d52a9-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d52a9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d52a9-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d52a9-115">See also</span></span>

- [<span data-ttu-id="d52a9-116">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="d52a9-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
