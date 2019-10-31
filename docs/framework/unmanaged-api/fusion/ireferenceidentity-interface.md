---
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
ms.openlocfilehash: 8f6a117d1e2fe76c271b0b014e6079370c8b4fe4
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127059"
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="a2282-102">IReferenceIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="a2282-102">IReferenceIdentity Interface</span></span>
<span data-ttu-id="a2282-103">Representa una referencia a la firma única de un objeto de código.</span><span class="sxs-lookup"><span data-stu-id="a2282-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="a2282-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="a2282-104">Methods</span></span>  
  
|<span data-ttu-id="a2282-105">Método</span><span class="sxs-lookup"><span data-stu-id="a2282-105">Method</span></span>|<span data-ttu-id="a2282-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="a2282-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="a2282-107">Obtiene un puntero de interfaz a una nueva instancia de `IReferenceIdentity` que es idéntica a esta `IReferenceIdentity`, excepto por los cambios de atributo especificados.</span><span class="sxs-lookup"><span data-stu-id="a2282-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="a2282-108">Obtiene un puntero de interfaz a una instancia de `IEnumIDENTITY_ATTRIBUTE` que contiene los atributos asociados a este `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="a2282-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="a2282-109">Obtiene el valor del atributo en el espacio de nombres especificado, con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="a2282-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="a2282-110">Establece el atributo que tiene el espacio de nombres especificado y el nombre especificado en el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="a2282-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="a2282-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a2282-111">Requirements</span></span>  
 <span data-ttu-id="a2282-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a2282-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a2282-113">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="a2282-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="a2282-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a2282-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2282-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="a2282-115">See also</span></span>

- [<span data-ttu-id="a2282-116">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="a2282-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
- [<span data-ttu-id="a2282-117">IEnumIDENTITY_ATTRIBUTE (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a2282-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](ienumidentity-attribute-interface.md)
