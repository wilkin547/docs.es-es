---
title: IDefinitionAppId (Interfaz)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IDefinitionAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionAppId
helpviewer_keywords:
- IDefinitionAppId interface [.NET Framework fusion]
ms.assetid: e72f2550-bdec-4a20-a2f4-2e14847266c1
topic_type:
- apiref
caps.latest.revision: 
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 247edbe300bbb93ddbdd4260109999fd33b08006
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="7d8da-102">IDefinitionAppId (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d8da-102">IDefinitionAppId Interface</span></span>
<span data-ttu-id="7d8da-103">Representa un identificador único para el código que define la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="7d8da-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="7d8da-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="7d8da-104">Methods</span></span>  
  
|<span data-ttu-id="7d8da-105">Método</span><span class="sxs-lookup"><span data-stu-id="7d8da-105">Method</span></span>|<span data-ttu-id="7d8da-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="7d8da-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="7d8da-107">Obtiene una cadena con formato que representa el código en este `IDefinitionAppId` objeto.</span><span class="sxs-lookup"><span data-stu-id="7d8da-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="7d8da-108">Establece el código de este `IDefinitionAppId` objeto especificado del valor de cadena con formato.</span><span class="sxs-lookup"><span data-stu-id="7d8da-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="7d8da-109">Obtiene un puntero de interfaz a una [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) objeto que contiene los ensamblados en la ruta de acceso de la aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="7d8da-109">Gets an interface pointer to an [IEnumDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="7d8da-110">Establece la ruta de acceso de la aplicación para el ensamblado en el ámbito actual en el valor al que hace referencia especificado [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) objeto.</span><span class="sxs-lookup"><span data-stu-id="7d8da-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](../../../../docs/framework/unmanaged-api/fusion/idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="7d8da-111">Obtiene un puntero a una representación de cadena del identificador del token para una suscripción a este `IDefinitionAppId` objeto.</span><span class="sxs-lookup"><span data-stu-id="7d8da-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="7d8da-112">Establece el identificador del token para una suscripción a este `IDefinitionAppId` objeto por el valor de cadena especificada.</span><span class="sxs-lookup"><span data-stu-id="7d8da-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7d8da-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d8da-113">Requirements</span></span>  
 <span data-ttu-id="7d8da-114">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d8da-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7d8da-115">**Encabezado:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="7d8da-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="7d8da-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d8da-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7d8da-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d8da-117">See Also</span></span>  
 [<span data-ttu-id="7d8da-118">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="7d8da-118">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
