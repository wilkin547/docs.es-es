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
ms.openlocfilehash: 7b1fc70380fff3c551c56043f49c2deda507e366
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/20/2020
ms.locfileid: "83703843"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="03bcc-102">ICLRHostProtectionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="03bcc-102">ICLRHostProtectionManager Interface</span></span>
<span data-ttu-id="03bcc-103">Permite al host bloquear la ejecución de clases, métodos, propiedades y campos administrados específicos en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="03bcc-103">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="03bcc-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="03bcc-104">Methods</span></span>  
  
|<span data-ttu-id="03bcc-105">Método</span><span class="sxs-lookup"><span data-stu-id="03bcc-105">Method</span></span>|<span data-ttu-id="03bcc-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="03bcc-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="03bcc-107">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="03bcc-107">SetEagerSerializeGrantSets</span></span>](iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="03bcc-108">Proporciona una garantía de que no se producirán nunca ciertas condiciones de carrera poco frecuentes que pueden provocar errores graves de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="03bcc-108">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="03bcc-109">Método SetProtectedCategories</span><span class="sxs-lookup"><span data-stu-id="03bcc-109">SetProtectedCategories Method</span></span>](iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="03bcc-110">Especifica las categorías de tipos administrados y miembros que se deben bloquear para que no se ejecuten en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="03bcc-110">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="03bcc-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03bcc-111">Requirements</span></span>  
 <span data-ttu-id="03bcc-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03bcc-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03bcc-113">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="03bcc-113">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="03bcc-114">**Biblioteca:** Se incluye como recurso en MSCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="03bcc-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="03bcc-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03bcc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03bcc-116">Consulta también</span><span class="sxs-lookup"><span data-stu-id="03bcc-116">See also</span></span>

- [<span data-ttu-id="03bcc-117">EApiCategories (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="03bcc-117">EApiCategories Enumeration</span></span>](eapicategories-enumeration.md)
- [<span data-ttu-id="03bcc-118">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="03bcc-118">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
