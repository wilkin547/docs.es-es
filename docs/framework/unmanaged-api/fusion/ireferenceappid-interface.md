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
ms.openlocfilehash: 2289a9a75311c9642a764844ee466adcc5838655
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54744354"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="30c7a-102">IReferenceAppId (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="30c7a-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="30c7a-103">Representa una referencia al identificador único para la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="30c7a-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="30c7a-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="30c7a-104">Methods</span></span>  
  
|<span data-ttu-id="30c7a-105">Método</span><span class="sxs-lookup"><span data-stu-id="30c7a-105">Method</span></span>|<span data-ttu-id="30c7a-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="30c7a-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="30c7a-107">Obtiene un puntero a una representación de cadena del identificador del código de la aplicación que hace referencia esta `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="30c7a-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="30c7a-108">Establece el identificador de código de la aplicación que hace referencia esta `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="30c7a-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="30c7a-109">Obtiene un puntero de interfaz a un `IEnumReferenceIdentity` instancia que contiene el `IReferenceIdentity` instancias que representan los miembros de este `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="30c7a-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="30c7a-110">Obtiene un puntero a una representación de cadena del identificador del token para una suscripción a este `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="30c7a-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="30c7a-111">Establece el identificador de token para una suscripción a este `IReferenceAppId` al valor de cadena especificado.</span><span class="sxs-lookup"><span data-stu-id="30c7a-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="30c7a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="30c7a-112">Requirements</span></span>  
 <span data-ttu-id="30c7a-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="30c7a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="30c7a-114">**Encabezado**: Isolation.h</span><span class="sxs-lookup"><span data-stu-id="30c7a-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="30c7a-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="30c7a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="30c7a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="30c7a-116">See also</span></span>
- [<span data-ttu-id="30c7a-117">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="30c7a-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="30c7a-118">IEnumReferenceIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="30c7a-118">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)
- [<span data-ttu-id="30c7a-119">IReferenceIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="30c7a-119">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
