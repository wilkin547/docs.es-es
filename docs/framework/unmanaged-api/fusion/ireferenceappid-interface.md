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
ms.openlocfilehash: 2484fa61c03b95e7cbdb452b92a68a2049701374
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429522"
---
# <a name="ireferenceappid-interface"></a><span data-ttu-id="1b8ad-102">IReferenceAppId (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1b8ad-102">IReferenceAppId Interface</span></span>
<span data-ttu-id="1b8ad-103">Representa una referencia al identificador único para la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="1b8ad-103">Represents a reference to the unique identifier for the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="1b8ad-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="1b8ad-104">Methods</span></span>  
  
|<span data-ttu-id="1b8ad-105">Método</span><span class="sxs-lookup"><span data-stu-id="1b8ad-105">Method</span></span>|<span data-ttu-id="1b8ad-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="1b8ad-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceAppId::get_CodeBase`|<span data-ttu-id="1b8ad-107">Obtiene un puntero a una representación de cadena del identificador del código de la aplicación que hace referencia esta `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="1b8ad-107">Gets a pointer to a string representation of the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_CodeBase`|<span data-ttu-id="1b8ad-108">Establece el identificador de código de la aplicación que hace referencia esta `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="1b8ad-108">Sets the code identifier for the application referenced by this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::EnumAppPath`|<span data-ttu-id="1b8ad-109">Obtiene un puntero de interfaz a una `IEnumReferenceIdentity` instancia que contiene el `IReferenceIdentity` instancias que representan los miembros de este `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="1b8ad-109">Gets an interface pointer to an `IEnumReferenceIdentity` instance containing the `IReferenceIdentity` instances that represent members of this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::get_SubscriptionId`|<span data-ttu-id="1b8ad-110">Obtiene un puntero a una representación de cadena del identificador del token para una suscripción a este `IReferenceAppId`.</span><span class="sxs-lookup"><span data-stu-id="1b8ad-110">Gets a pointer to a string representation of the token identifier for a subscription to this `IReferenceAppId`.</span></span>|  
|`IReferenceAppId::put_SubscriptionId`|<span data-ttu-id="1b8ad-111">Establece el identificador del token para una suscripción a este `IReferenceAppId` en el valor de cadena especificado.</span><span class="sxs-lookup"><span data-stu-id="1b8ad-111">Sets the token identifier for a subscription to this `IReferenceAppId` to the specified string value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1b8ad-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1b8ad-112">Requirements</span></span>  
 <span data-ttu-id="1b8ad-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1b8ad-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1b8ad-114">**Encabezado:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="1b8ad-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="1b8ad-115">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1b8ad-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1b8ad-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="1b8ad-116">See Also</span></span>  
 [<span data-ttu-id="1b8ad-117">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="1b8ad-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="1b8ad-118">IEnumReferenceIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1b8ad-118">IEnumReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumreferenceidentity-interface.md)  
 [<span data-ttu-id="1b8ad-119">IReferenceIdentity (interfaz)</span><span class="sxs-lookup"><span data-stu-id="1b8ad-119">IReferenceIdentity Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ireferenceidentity-interface.md)
