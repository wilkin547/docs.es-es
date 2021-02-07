---
description: 'Más información sobre: IDefinitionAppId (interfaz)'
title: IDefinitionAppId (Interfaz)
ms.date: 03/30/2017
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
ms.openlocfilehash: 3c68044e7e747521e190fad404e89d6d0a994611
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760672"
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="dea8b-103">IDefinitionAppId (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dea8b-103">IDefinitionAppId Interface</span></span>

<span data-ttu-id="dea8b-104">Representa un identificador único para el código que define la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="dea8b-104">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dea8b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="dea8b-105">Methods</span></span>  
  
|<span data-ttu-id="dea8b-106">Método</span><span class="sxs-lookup"><span data-stu-id="dea8b-106">Method</span></span>|<span data-ttu-id="dea8b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="dea8b-107">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="dea8b-108">Obtiene una cadena con formato que representa el código de este `IDefinitionAppId` objeto.</span><span class="sxs-lookup"><span data-stu-id="dea8b-108">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="dea8b-109">Establece el código de este `IDefinitionAppId` objeto en el valor de cadena con formato especificado.</span><span class="sxs-lookup"><span data-stu-id="dea8b-109">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="dea8b-110">Obtiene un puntero de interfaz a un objeto [IEnumDefinitionIdentity (](ienumdefinitionidentity-interface.md) que contiene los ensamblados de la ruta de acceso de la aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="dea8b-110">Gets an interface pointer to an [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="dea8b-111">Establece la ruta de acceso de la aplicación para el ensamblado en el ámbito actual en el valor al que hace referencia el objeto [IDefinitionIdentity](idefinitionidentity-interface.md) especificado.</span><span class="sxs-lookup"><span data-stu-id="dea8b-111">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="dea8b-112">Obtiene un puntero a una representación de cadena del identificador de token para una suscripción a este `IDefinitionAppId` objeto.</span><span class="sxs-lookup"><span data-stu-id="dea8b-112">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="dea8b-113">Establece el identificador de token de una suscripción a este `IDefinitionAppId` objeto en el valor de cadena especificado.</span><span class="sxs-lookup"><span data-stu-id="dea8b-113">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dea8b-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dea8b-114">Requirements</span></span>  

 <span data-ttu-id="dea8b-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dea8b-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dea8b-116">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="dea8b-116">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="dea8b-117">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dea8b-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dea8b-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="dea8b-118">See also</span></span>

- [<span data-ttu-id="dea8b-119">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="dea8b-119">Fusion Interfaces</span></span>](fusion-interfaces.md)
