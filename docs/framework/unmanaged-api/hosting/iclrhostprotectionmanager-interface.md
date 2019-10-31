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
ms.openlocfilehash: 0487a87420c888cf5466f54c28c2d89623260add
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141050"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="d3716-102">ICLRHostProtectionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3716-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="d3716-103">Permite al host bloquear la ejecución de clases, métodos, propiedades y campos administrados específicos en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="d3716-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d3716-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d3716-104">Methods</span></span>  
  
|<span data-ttu-id="d3716-105">Método</span><span class="sxs-lookup"><span data-stu-id="d3716-105">Method</span></span>|<span data-ttu-id="d3716-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d3716-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="d3716-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="d3716-107">SetEagerSerializeGrantSets</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="d3716-108">Proporciona una garantía de que no se producirán nunca ciertas condiciones de carrera poco frecuentes que pueden provocar errores graves de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="d3716-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="d3716-109">SetProtectedCategories (método)</span><span class="sxs-lookup"><span data-stu-id="d3716-109">SetProtectedCategories Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="d3716-110">Especifica las categorías de tipos administrados y miembros que se deben bloquear para que no se ejecuten en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="d3716-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d3716-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d3716-111">Requirements</span></span>  
 <span data-ttu-id="d3716-112">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d3716-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d3716-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="d3716-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="d3716-114">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d3716-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="d3716-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d3716-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d3716-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="d3716-116">See also</span></span>

- [<span data-ttu-id="d3716-117">EApiCategories (enumeración)</span><span class="sxs-lookup"><span data-stu-id="d3716-117">EApiCategories Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/eapicategories-enumeration.md)
- [<span data-ttu-id="d3716-118">ICLRControl (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d3716-118">ICLRControl Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrcontrol-interface.md)
