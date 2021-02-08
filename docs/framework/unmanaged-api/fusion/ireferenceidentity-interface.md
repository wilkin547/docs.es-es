---
description: 'Más información acerca de: IReferenceIdentity (interfaz)'
title: IReferenceIdentity (Interfaz)
ms.date: 03/30/2017
api_name:
- IReferenceIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IReferenceIdentity
helpviewer_keywords:
- IReferenceIdentity interface [.NET Framework fusion]
ms.assetid: 9180ac5a-7019-4716-9f83-8a91d157239a
topic_type:
- apiref
ms.openlocfilehash: a29aaa1f4fb928c136af4168619d27900537c779
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800050"
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="e3567-103">IReferenceIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3567-103">IReferenceIdentity Interface</span></span>

<span data-ttu-id="e3567-104">Representa una referencia a la firma única de un objeto de código.</span><span class="sxs-lookup"><span data-stu-id="e3567-104">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e3567-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="e3567-105">Methods</span></span>  
  
|<span data-ttu-id="e3567-106">Método</span><span class="sxs-lookup"><span data-stu-id="e3567-106">Method</span></span>|<span data-ttu-id="e3567-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="e3567-107">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="e3567-108">Obtiene un puntero de interfaz a una nueva `IReferenceIdentity` instancia de que es idéntica a esta `IReferenceIdentity` , salvo por los cambios de atributo especificados.</span><span class="sxs-lookup"><span data-stu-id="e3567-108">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="e3567-109">Obtiene un puntero de interfaz a una `IEnumIDENTITY_ATTRIBUTE` instancia de que contiene los atributos asociados a este `IReferenceIdentity` .</span><span class="sxs-lookup"><span data-stu-id="e3567-109">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="e3567-110">Obtiene el valor del atributo en el espacio de nombres especificado, con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="e3567-110">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="e3567-111">Establece el atributo que tiene el espacio de nombres especificado y el nombre especificado en el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="e3567-111">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e3567-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e3567-112">Requirements</span></span>  

 <span data-ttu-id="e3567-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e3567-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e3567-114">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="e3567-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="e3567-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e3567-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e3567-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="e3567-116">See also</span></span>

- [<span data-ttu-id="e3567-117">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="e3567-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="e3567-118">IEnumIDENTITY_ATTRIBUTE (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e3567-118">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)
