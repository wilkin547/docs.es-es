---
description: 'Más información acerca de: interfaz ICLRHostProtectionManager'
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
ms.openlocfilehash: 60d27a8c1a24720bbfdcde52a5495425279d5ac4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689253"
---
# <a name="iclrhostprotectionmanager-interface"></a><span data-ttu-id="04ff1-103">ICLRHostProtectionManager (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04ff1-103">ICLRHostProtectionManager Interface</span></span>

<span data-ttu-id="04ff1-104">Permite al host bloquear la ejecución de clases, métodos, propiedades y campos administrados específicos en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="04ff1-104">Enables the host to block specific managed classes, methods, properties, and fields from running in partially trusted code.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="04ff1-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="04ff1-105">Methods</span></span>  
  
|<span data-ttu-id="04ff1-106">Método</span><span class="sxs-lookup"><span data-stu-id="04ff1-106">Method</span></span>|<span data-ttu-id="04ff1-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="04ff1-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="04ff1-108">SetEagerSerializeGrantSets</span><span class="sxs-lookup"><span data-stu-id="04ff1-108">SetEagerSerializeGrantSets</span></span>](iclrhostprotectionmanager-seteagerserializegrantsets-method.md)|<span data-ttu-id="04ff1-109">Proporciona una garantía de que no se producirán nunca ciertas condiciones de carrera poco frecuentes que pueden provocar errores graves de Common Language Runtime (CLR).</span><span class="sxs-lookup"><span data-stu-id="04ff1-109">Provides a guarantee that certain rare race conditions that can cause fatal common language runtime (CLR) errors will never arise.</span></span>|  
|[<span data-ttu-id="04ff1-110">Método SetProtectedCategories</span><span class="sxs-lookup"><span data-stu-id="04ff1-110">SetProtectedCategories Method</span></span>](iclrhostprotectionmanager-setprotectedcategories-method.md)|<span data-ttu-id="04ff1-111">Especifica las categorías de tipos administrados y miembros que se deben bloquear para que no se ejecuten en código de confianza parcial.</span><span class="sxs-lookup"><span data-stu-id="04ff1-111">Specifies the categories of managed types and members that should be blocked from running in partially trusted code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="04ff1-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04ff1-112">Requirements</span></span>  

 <span data-ttu-id="04ff1-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04ff1-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04ff1-114">**Encabezado:** MSCorEE. h</span><span class="sxs-lookup"><span data-stu-id="04ff1-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="04ff1-115">**Biblioteca:** Se incluye como un recurso en MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="04ff1-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="04ff1-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04ff1-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04ff1-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="04ff1-117">See also</span></span>

- [<span data-ttu-id="04ff1-118">EApiCategories (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="04ff1-118">EApiCategories Enumeration</span></span>](eapicategories-enumeration.md)
- [<span data-ttu-id="04ff1-119">ICLRControl (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="04ff1-119">ICLRControl Interface</span></span>](iclrcontrol-interface.md)
