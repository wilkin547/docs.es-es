---
title: ICLRHostProtectionManager (Interfaz)
ms.date: 03/30/2017
api_name:
- ICLRHostProtectionManager
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRHostProtectionManager
helpviewer_keywords:
- ICLRHostProtectionManager interface [.NET Framework hosting]
ms.assetid: ce2770ae-23d0-45d9-8bcf-46504ac5020e
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fd096344c987d8901f0baab86e370abbb03528e5
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61944678"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="5e4f2-102">ICLRHostProtectionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e4f2-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="5e4f2-103">Permite que el host bloquear clases administradas específicas, métodos, propiedades y campos se ejecuten en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="5e4f2-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="5e4f2-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="5e4f2-104">Methods</span></span>  
  
|<span data-ttu-id="5e4f2-105">Método</span><span class="sxs-lookup"><span data-stu-id="5e4f2-105">Method</span></span>|<span data-ttu-id="5e4f2-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="5e4f2-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="5e4f2-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="5e4f2-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="5e4f2-108">Proporciona una garantía de que nunca se producirán ciertas condiciones de carrera poco frecuente que pueden causar grave de common language runtime (CLR) errores.</span><span class="sxs-lookup"><span data-stu-id="5e4f2-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="5e4f2-109">SetProtectedCategories (método)</span><span class="sxs-lookup"><span data-stu-id="5e4f2-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="5e4f2-110">Especifica las categorías de tipos administrados y miembros que se deben bloquear su ejecución en el código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="5e4f2-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5e4f2-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5e4f2-111">Requirements</span></span>  
 <span data-ttu-id="5e4f2-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5e4f2-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5e4f2-113">**Encabezado**: MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="5e4f2-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="5e4f2-114">**Biblioteca:** Incluye como recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5e4f2-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="5e4f2-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5e4f2-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5e4f2-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="5e4f2-116">See also</span></span>

- [<span data-ttu-id="5e4f2-117">EApiCategories (enumeración)</span><span class="sxs-lookup"><span data-stu-id="5e4f2-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="5e4f2-118">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="5e4f2-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
