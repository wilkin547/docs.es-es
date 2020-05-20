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
ms.openlocfilehash: fbf501d906ecc0bf55719fa33d1af2d4db1cc2ef
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617105"
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="fa2de-102">IApartmentCallback (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="fa2de-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="fa2de-103">Proporciona métodos para crear devoluciones de llamada dentro de un contenedor.</span><span class="sxs-lookup"><span data-stu-id="fa2de-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="fa2de-104">Un *Apartamento* es un contenedor lógico dentro de un proceso para objetos que comparten los mismos requisitos de acceso de subprocesos.</span><span class="sxs-lookup"><span data-stu-id="fa2de-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fa2de-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="fa2de-105">Methods</span></span>  
  
|<span data-ttu-id="fa2de-106">Método</span><span class="sxs-lookup"><span data-stu-id="fa2de-106">Method</span></span>|<span data-ttu-id="fa2de-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="fa2de-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="fa2de-108">Método DoCallback</span><span class="sxs-lookup"><span data-stu-id="fa2de-108">DoCallback Method</span></span>](iapartmentcallback-docallback-method.md)|<span data-ttu-id="fa2de-109">Ejecuta la función especificada dentro de un contenedor.</span><span class="sxs-lookup"><span data-stu-id="fa2de-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fa2de-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fa2de-110">Requirements</span></span>  
 <span data-ttu-id="fa2de-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fa2de-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fa2de-112">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="fa2de-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fa2de-113">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fa2de-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fa2de-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fa2de-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fa2de-115">Consulta también</span><span class="sxs-lookup"><span data-stu-id="fa2de-115">See also</span></span>

- [<span data-ttu-id="fa2de-116">Interfaces de hospedaje</span><span class="sxs-lookup"><span data-stu-id="fa2de-116">Hosting Interfaces</span></span>](hosting-interfaces.md)
