---
description: 'Más información sobre: interfaz IDefinitionIdentity'
title: IDefinitionIdentity (Interfaz)
ms.date: 03/30/2017
api_name:
- IDefinitionIdentity
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IDefinitionIdentity
helpviewer_keywords:
- IDefinitionIdentity interface [.NET Framework fusion]
ms.assetid: ce5ba888-5fbe-4efd-91cf-f0ff94d8428b
topic_type:
- apiref
ms.openlocfilehash: 3471879cc822b655b786dd9d8234950cb4b99c1d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760659"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="4f035-103">IDefinitionIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4f035-103">IDefinitionIdentity Interface</span></span>

<span data-ttu-id="4f035-104">Representa la firma única del código que define la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="4f035-104">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4f035-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4f035-105">Methods</span></span>  
  
|<span data-ttu-id="4f035-106">Método</span><span class="sxs-lookup"><span data-stu-id="4f035-106">Method</span></span>|<span data-ttu-id="4f035-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4f035-107">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="4f035-108">Obtiene un puntero de interfaz a un nuevo `IDefinitionIdentity` objeto que es idéntico a este `IDefinitionIdentity` , excepto por los cambios de atributo especificados.</span><span class="sxs-lookup"><span data-stu-id="4f035-108">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="4f035-109">Obtiene un puntero de interfaz a un objeto [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) que contiene los atributos asociados a este `IDefinitionIdentity` .</span><span class="sxs-lookup"><span data-stu-id="4f035-109">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="4f035-110">Obtiene el valor del atributo con el nombre especificado en el espacio de nombres especificado.</span><span class="sxs-lookup"><span data-stu-id="4f035-110">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="4f035-111">Establece el atributo que tiene el nombre especificado en el espacio de nombres especificado en el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="4f035-111">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4f035-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4f035-112">Requirements</span></span>  

 <span data-ttu-id="4f035-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4f035-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4f035-114">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="4f035-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="4f035-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4f035-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4f035-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="4f035-116">See also</span></span>

- [<span data-ttu-id="4f035-117">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="4f035-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
