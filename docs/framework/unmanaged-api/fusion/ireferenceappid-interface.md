---
description: 'Más información sobre: IReferenceAppId (interfaz)'
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
ms.openlocfilehash: 66838d6ae66aa7de05d899e9fa980308718e2a38
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800076"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="81fae-103">IReferenceAppId (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="81fae-103">IReferenceAppId Interface</span></span>

<span data-ttu-id="81fae-104">Representa una referencia al identificador único de la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="81fae-104">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="81fae-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="81fae-105">Methods</span></span>  
  
|<span data-ttu-id="81fae-106">Método</span><span class="sxs-lookup"><span data-stu-id="81fae-106">Method</span></span>|<span data-ttu-id="81fae-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="81fae-107">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="81fae-108">Obtiene un puntero a una representación de cadena del identificador de código para la aplicación a la que hace referencia este `IReferenceAppId` .</span><span class="sxs-lookup"><span data-stu-id="81fae-108">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="81fae-109">Establece el identificador de código de la aplicación a la que hace referencia este `IReferenceAppId` .</span><span class="sxs-lookup"><span data-stu-id="81fae-109">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="81fae-110">Obtiene un puntero de interfaz a una `IEnumReferenceIdentity` instancia de que contiene las `IReferenceIdentity` instancias de que representan a los miembros de este objeto `IReferenceAppId` .</span><span class="sxs-lookup"><span data-stu-id="81fae-110">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="81fae-111">Obtiene un puntero a una representación de cadena del identificador de token de una suscripción a este `IReferenceAppId` .</span><span class="sxs-lookup"><span data-stu-id="81fae-111">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="81fae-112">Establece el identificador de token de una suscripción en `IReferenceAppId` el valor de cadena especificado.</span><span class="sxs-lookup"><span data-stu-id="81fae-112">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="81fae-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81fae-113">Requirements</span></span>  

 <span data-ttu-id="81fae-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81fae-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81fae-115">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="81fae-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="81fae-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="81fae-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81fae-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="81fae-117">See also</span></span>

- [<span data-ttu-id="81fae-118">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="81fae-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="81fae-119">IEnumReferenceIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="81fae-119">IEnumReferenceIdentity Interface</span></span>](ienumreferenceidentity-interface.md)
- [<span data-ttu-id="81fae-120">IReferenceIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="81fae-120">IReferenceIdentity Interface</span></span>](ireferenceidentity-interface.md)
