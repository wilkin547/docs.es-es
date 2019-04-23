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
ms.openlocfilehash: 4ff23330f307c10eac134048de39a6e19a67c75b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59192672"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="cd90b-102">IDefinitionIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="cd90b-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="cd90b-103">Representa la firma única del código que define la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="cd90b-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="cd90b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="cd90b-104">Methods</span></span>  
  
|<span data-ttu-id="cd90b-105">Método</span><span class="sxs-lookup"><span data-stu-id="cd90b-105">Method</span></span>|<span data-ttu-id="cd90b-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="cd90b-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="cd90b-107">Obtiene un puntero de interfaz a una nueva `IDefinitionIdentity` objeto que es idéntica a esta `IDefinitionIdentity`, excepto los cambios de atributo especificado.</span><span class="sxs-lookup"><span data-stu-id="cd90b-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="cd90b-108">Obtiene un puntero de interfaz a un [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) objeto que contiene los atributos asociados con este `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="cd90b-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="cd90b-109">Obtiene el valor del atributo con el nombre especificado en el espacio de nombres especificado.</span><span class="sxs-lookup"><span data-stu-id="cd90b-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="cd90b-110">Establece el atributo que tiene el nombre especificado en el espacio de nombres especificado en el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="cd90b-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cd90b-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cd90b-111">Requirements</span></span>  
 <span data-ttu-id="cd90b-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cd90b-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cd90b-113">**Encabezado**: Isolation.h</span><span class="sxs-lookup"><span data-stu-id="cd90b-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="cd90b-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cd90b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cd90b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cd90b-115">See also</span></span>

- [<span data-ttu-id="cd90b-116">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="cd90b-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
