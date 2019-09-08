---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 929909a7f2c4fa1799c8fed94787b8f853c7eac2
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796508"
---
# <a name="idefinitionappid-interface"></a><span data-ttu-id="c6d6e-102">IDefinitionAppId (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c6d6e-102">IDefinitionAppId Interface</span></span>
<span data-ttu-id="c6d6e-103">Representa un identificador único para el código que define la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="c6d6e-103">Represents a unique identifier for the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c6d6e-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c6d6e-104">Methods</span></span>  
  
|<span data-ttu-id="c6d6e-105">Método</span><span class="sxs-lookup"><span data-stu-id="c6d6e-105">Method</span></span>|<span data-ttu-id="c6d6e-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c6d6e-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionAppId::get_Codebase`|<span data-ttu-id="c6d6e-107">Obtiene una cadena con formato que representa el código de `IDefinitionAppId` este objeto.</span><span class="sxs-lookup"><span data-stu-id="c6d6e-107">Gets a formatted string that represents the code in this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_Codebase`|<span data-ttu-id="c6d6e-108">Establece el código de este `IDefinitionAppId` objeto en el valor de cadena con formato especificado.</span><span class="sxs-lookup"><span data-stu-id="c6d6e-108">Sets the code of this `IDefinitionAppId` object to the specified formatted string value.</span></span>|  
|`IDefinitionAppId::EnumAppPath`|<span data-ttu-id="c6d6e-109">Obtiene un puntero de interfaz a un objeto [IEnumDefinitionIdentity (](ienumdefinitionidentity-interface.md) que contiene los ensamblados de la ruta de acceso de la aplicación actual.</span><span class="sxs-lookup"><span data-stu-id="c6d6e-109">Gets an interface pointer to an [IEnumDefinitionIdentity](ienumdefinitionidentity-interface.md) object that contains the assemblies in the current application path.</span></span>|  
|`IDefinitionAppId::SetAppPath`|<span data-ttu-id="c6d6e-110">Establece la ruta de acceso de la aplicación para el ensamblado en el ámbito actual en el valor al que hace referencia el objeto [IDefinitionIdentity](idefinitionidentity-interface.md) especificado.</span><span class="sxs-lookup"><span data-stu-id="c6d6e-110">Sets the application path for the assembly in the current scope to the value referenced by the specified [IDefinitionIdentity](idefinitionidentity-interface.md) object.</span></span>|  
|`IDefinitionAppId::get_SubscriptionId`|<span data-ttu-id="c6d6e-111">Obtiene un puntero a una representación de cadena del identificador de token para una suscripción a este `IDefinitionAppId` objeto.</span><span class="sxs-lookup"><span data-stu-id="c6d6e-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IDefinitionAppId` object.</span></span>|  
|`IDefinitionAppId::put_SubscriptionId`|<span data-ttu-id="c6d6e-112">Establece el identificador de token de una suscripción a este `IDefinitionAppId` objeto en el valor de cadena especificado.</span><span class="sxs-lookup"><span data-stu-id="c6d6e-112">Sets the token identifier for a subscription to this `IDefinitionAppId` object to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c6d6e-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c6d6e-113">Requirements</span></span>  
 <span data-ttu-id="c6d6e-114">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c6d6e-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c6d6e-115">**Encabezado**: Isolation. h</span><span class="sxs-lookup"><span data-stu-id="c6d6e-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="c6d6e-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6d6e-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c6d6e-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="c6d6e-117">See also</span></span>

- [<span data-ttu-id="c6d6e-118">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="c6d6e-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
