---
title: IDefinitionIdentity (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IDefinitionIdentity
api_location: fusion.dll
api_type: COM
f1_keywords: IDefinitionIdentity
helpviewer_keywords: IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b074ae2a0a4e4e65f0402ff35888b557b00dd071
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="c2fc5-102">IDefinitionIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c2fc5-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="c2fc5-103">Representa la firma única del código que define la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="c2fc5-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c2fc5-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c2fc5-104">Methods</span></span>  
  
|<span data-ttu-id="c2fc5-105">Método</span><span class="sxs-lookup"><span data-stu-id="c2fc5-105">Method</span></span>|<span data-ttu-id="c2fc5-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c2fc5-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="c2fc5-107">Obtiene un puntero de interfaz a una nueva `IDefinitionIdentity` objeto que es idéntico a `IDefinitionIdentity`, excepto para los cambios de atributo especificado.</span><span class="sxs-lookup"><span data-stu-id="c2fc5-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="c2fc5-108">Obtiene un puntero de interfaz a una [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) objeto que contiene los atributos asociados a este `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="c2fc5-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="c2fc5-109">Obtiene el valor del atributo con el nombre especificado en el espacio de nombres especificado.</span><span class="sxs-lookup"><span data-stu-id="c2fc5-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="c2fc5-110">Establece el atributo que tiene el nombre especificado en el espacio de nombres especificado en el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="c2fc5-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c2fc5-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c2fc5-111">Requirements</span></span>  
 <span data-ttu-id="c2fc5-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c2fc5-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c2fc5-113">**Encabezado:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="c2fc5-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="c2fc5-114">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c2fc5-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c2fc5-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c2fc5-115">See Also</span></span>  
 [<span data-ttu-id="c2fc5-116">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="c2fc5-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
