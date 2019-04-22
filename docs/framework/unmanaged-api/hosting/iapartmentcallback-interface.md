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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: db933716cc0602ecda5da8a72726408ae4910179
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59129810"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="8f651-102">IApartmentCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="8f651-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="8f651-103">Proporciona métodos para hacer que las devoluciones de llamada dentro de un apartamento.</span><span class="sxs-lookup"><span data-stu-id="8f651-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="8f651-104">Un *apartamento* es un contenedor lógico dentro de un proceso para los objetos que comparten los mismos requisitos de acceso de subproceso.</span><span class="sxs-lookup"><span data-stu-id="8f651-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8f651-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="8f651-105">Methods</span></span>  
  
|<span data-ttu-id="8f651-106">Método</span><span class="sxs-lookup"><span data-stu-id="8f651-106">Method</span></span>|<span data-ttu-id="8f651-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="8f651-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8f651-108">DoCallback (método)</span><span class="sxs-lookup"><span data-stu-id="8f651-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="8f651-109">Ejecuta la función especificada dentro de un apartamento.</span><span class="sxs-lookup"><span data-stu-id="8f651-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8f651-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8f651-110">Requirements</span></span>  
 <span data-ttu-id="8f651-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8f651-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f651-112">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="8f651-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="8f651-113">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8f651-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="8f651-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f651-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f651-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="8f651-115">See also</span></span>

- [<span data-ttu-id="8f651-116">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="8f651-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
