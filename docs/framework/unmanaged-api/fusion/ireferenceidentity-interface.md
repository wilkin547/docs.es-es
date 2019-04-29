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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dd46ea26532074c9ea42da4d07a38ed583aad076
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61789687"
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="d70ac-102">IReferenceIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d70ac-102">IReferenceIdentity Interface</span></span>
<span data-ttu-id="d70ac-103">Representa una referencia a la firma única de un objeto de código.</span><span class="sxs-lookup"><span data-stu-id="d70ac-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="d70ac-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="d70ac-104">Methods</span></span>  
  
|<span data-ttu-id="d70ac-105">Método</span><span class="sxs-lookup"><span data-stu-id="d70ac-105">Method</span></span>|<span data-ttu-id="d70ac-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="d70ac-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="d70ac-107">Obtiene un puntero de interfaz a una nueva `IReferenceIdentity` que es idéntica a esta instancia de `IReferenceIdentity`, excepto los cambios de atributo especificado.</span><span class="sxs-lookup"><span data-stu-id="d70ac-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="d70ac-108">Obtiene un puntero de interfaz a un `IEnumIDENTITY_ATTRIBUTE` instancia que contiene los atributos asociados con este `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="d70ac-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="d70ac-109">Obtiene el valor del atributo en el espacio de nombres especificado, con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="d70ac-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="d70ac-110">Establece el atributo que tiene el espacio de nombres especificado y el nombre especificado en el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="d70ac-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d70ac-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d70ac-111">Requirements</span></span>  
 <span data-ttu-id="d70ac-112">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d70ac-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d70ac-113">**Encabezado**: Isolation.h</span><span class="sxs-lookup"><span data-stu-id="d70ac-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="d70ac-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d70ac-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d70ac-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="d70ac-115">See also</span></span>

- [<span data-ttu-id="d70ac-116">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="d70ac-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
- [<span data-ttu-id="d70ac-117">IEnumIDENTITY_ATTRIBUTE (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d70ac-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
