---
title: IDefinitionIdentity (Interfaz)
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 401c23e44cc473d0a27a82a00343852693cb0f2e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429350"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="98080-102">IDefinitionIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="98080-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="98080-103">Representa la firma única del código que define la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="98080-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="98080-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="98080-104">Methods</span></span>  
  
|<span data-ttu-id="98080-105">Método</span><span class="sxs-lookup"><span data-stu-id="98080-105">Method</span></span>|<span data-ttu-id="98080-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="98080-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="98080-107">Obtiene un puntero de interfaz a una nueva `IDefinitionIdentity` objeto que es idéntico a `IDefinitionIdentity`, excepto para los cambios de atributo especificado.</span><span class="sxs-lookup"><span data-stu-id="98080-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="98080-108">Obtiene un puntero de interfaz a una [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) objeto que contiene los atributos asociados a este `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="98080-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="98080-109">Obtiene el valor del atributo con el nombre especificado en el espacio de nombres especificado.</span><span class="sxs-lookup"><span data-stu-id="98080-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="98080-110">Establece el atributo que tiene el nombre especificado en el espacio de nombres especificado en el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="98080-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="98080-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98080-111">Requirements</span></span>  
 <span data-ttu-id="98080-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98080-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98080-113">**Encabezado:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="98080-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="98080-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="98080-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98080-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="98080-115">See Also</span></span>  
 [<span data-ttu-id="98080-116">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="98080-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
