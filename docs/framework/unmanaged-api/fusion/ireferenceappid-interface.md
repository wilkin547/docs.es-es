---
title: IReferenceAppId (Interfaz)
ms.date: 03/30/2017
api_name:
- IReferenceAppId
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceAppId
helpviewer_keywords:
- IReferenceAppId interface [.NET Framework fusion]
ms.assetid: 8eb9e565-f358-43ce-900e-a8f8a5aa6cfb
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 522ed80f161f114af25e1fa7ad041c8238073d6f
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796370"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="07609-102">IReferenceAppId (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="07609-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="07609-103">Representa una referencia al identificador único de la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="07609-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="07609-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="07609-104">Methods</span></span>  
  
|<span data-ttu-id="07609-105">Método</span><span class="sxs-lookup"><span data-stu-id="07609-105">Method</span></span>|<span data-ttu-id="07609-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="07609-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="07609-107">Obtiene un puntero a una representación de cadena del identificador de código para la aplicación a la que hace `IReferenceAppId`referencia este.</span><span class="sxs-lookup"><span data-stu-id="07609-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="07609-108">Establece el identificador de código de la aplicación a la que hace `IReferenceAppId`referencia este.</span><span class="sxs-lookup"><span data-stu-id="07609-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="07609-109">Obtiene un puntero de interfaz a `IEnumReferenceIdentity` una instancia de `IReferenceIdentity` que contiene las instancias de que `IReferenceAppId`representan a los miembros de este objeto.</span><span class="sxs-lookup"><span data-stu-id="07609-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="07609-110">Obtiene un puntero a una representación de cadena del identificador de token de una suscripción a este `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="07609-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="07609-111">Establece el identificador de token de una suscripción en `IReferenceAppId` el valor de cadena especificado.</span><span class="sxs-lookup"><span data-stu-id="07609-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="07609-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="07609-112">Requirements</span></span>  
 <span data-ttu-id="07609-113">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07609-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07609-114">**Encabezado**: Isolation. h</span><span class="sxs-lookup"><span data-stu-id="07609-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="07609-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07609-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07609-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="07609-116">See also</span></span>

- [<span data-ttu-id="07609-117">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="07609-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="07609-118">IEnumReferenceIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="07609-118">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)
- [<span data-ttu-id="07609-119">IReferenceIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="07609-119">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
