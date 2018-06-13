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
ms.openlocfilehash: 4708fa173725e4c91a13f5b92cdbb1fdf8a8a4d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33432108"
---
# <a name="ireferenceidentity-interface"></a><span data-ttu-id="c5282-102">IReferenceIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c5282-102">IReferenceIdentity Interface</span></span>
<span data-ttu-id="c5282-103">Representa una referencia a la firma única de un objeto de código.</span><span class="sxs-lookup"><span data-stu-id="c5282-103">Represents a reference to the unique signature of a code object.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c5282-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="c5282-104">Methods</span></span>  
  
|<span data-ttu-id="c5282-105">Método</span><span class="sxs-lookup"><span data-stu-id="c5282-105">Method</span></span>|<span data-ttu-id="c5282-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="c5282-106">Description</span></span>|  
|------------|-----------------|  
|`IReferenceIdentity::Clone`|<span data-ttu-id="c5282-107">Obtiene un puntero de interfaz a una nueva `IReferenceIdentity` instancia que es idéntico a `IReferenceIdentity`, excepto para los cambios de atributo especificado.</span><span class="sxs-lookup"><span data-stu-id="c5282-107">Gets an interface pointer to a new `IReferenceIdentity` instance that is identical to this `IReferenceIdentity`, except for the specified attribute changes.</span></span>|  
|`IReferenceIdentity::EnumAttributes`|<span data-ttu-id="c5282-108">Obtiene un puntero de interfaz a una `IEnumIDENTITY_ATTRIBUTE` instancia que contiene los atributos asociados a este `IReferenceIdentity`.</span><span class="sxs-lookup"><span data-stu-id="c5282-108">Gets an interface pointer to an `IEnumIDENTITY_ATTRIBUTE` instance that contains the attributes associated with this `IReferenceIdentity`.</span></span>|  
|`IReferenceIdentity::GetAttribute`|<span data-ttu-id="c5282-109">Obtiene el valor del atributo en el espacio de nombres especificado, con el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="c5282-109">Gets the value of the attribute in the specified namespace, with the specified name.</span></span>|  
|`IReferenceIdentity::SetAttribute`|<span data-ttu-id="c5282-110">Establece el atributo que tiene el espacio de nombres especificado y el nombre especificado en el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="c5282-110">Sets the attribute that has the specified namespace and the specified name to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c5282-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c5282-111">Requirements</span></span>  
 <span data-ttu-id="c5282-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c5282-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c5282-113">**Encabezado:** Isolation.h</span><span class="sxs-lookup"><span data-stu-id="c5282-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="c5282-114">**Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c5282-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c5282-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="c5282-115">See Also</span></span>  
 [<span data-ttu-id="c5282-116">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="c5282-116">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)  
 [<span data-ttu-id="c5282-117">IEnumIDENTITY_ATTRIBUTE (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c5282-117">IEnumIDENTITY_ATTRIBUTE Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/ienumidentity-attribute-interface.md)
