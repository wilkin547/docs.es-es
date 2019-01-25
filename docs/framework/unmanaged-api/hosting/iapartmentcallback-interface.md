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
ms.openlocfilehash: bc3f9e8c581bc95bea8cfeb549177966eae22a43
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54584498"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="a7896-102">IApartmentCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a7896-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="a7896-103">Proporciona métodos para hacer que las devoluciones de llamada dentro de un apartamento.</span><span class="sxs-lookup"><span data-stu-id="a7896-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="a7896-104">Un *apartamento* es un contenedor lógico dentro de un proceso para los objetos que comparten los mismos requisitos de acceso de subproceso.</span><span class="sxs-lookup"><span data-stu-id="a7896-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a7896-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="a7896-105">Methods</span></span>  
  
|<span data-ttu-id="a7896-106">Método</span><span class="sxs-lookup"><span data-stu-id="a7896-106">Method</span></span>|<span data-ttu-id="a7896-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="a7896-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="a7896-108">DoCallback (método)</span><span class="sxs-lookup"><span data-stu-id="a7896-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="a7896-109">Ejecuta la función especificada dentro de un apartamento.</span><span class="sxs-lookup"><span data-stu-id="a7896-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a7896-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a7896-110">Requirements</span></span>  
 <span data-ttu-id="a7896-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a7896-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7896-112">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="a7896-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="a7896-113">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a7896-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="a7896-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7896-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7896-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a7896-115">See also</span></span>
- [<span data-ttu-id="a7896-116">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="a7896-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
