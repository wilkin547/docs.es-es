---
description: 'Más información acerca de: interfaz IEnumIDENTITY_ATTRIBUTE'
title: IEnumIDENTITY_ATTRIBUTE (Interfaz)
ms.date: 03/30/2017
api_name:
- IEnumIDENTITY_ATTRIBUTE
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IEnumIDENTITY_ATTRIBUTE
helpviewer_keywords:
- IEnumIDENTITY_ATTRIBUTE interface [.NET Framework fusion]
ms.assetid: c2ec2748-e9ae-4e1b-80db-6fcec5cb81a1
topic_type:
- apiref
ms.openlocfilehash: b621a722e35d5b31f487e8823b1627fdfe1e7888
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99800154"
---
# <a name="ienumidentity_attribute-interface"></a><span data-ttu-id="4254b-103">IEnumIDENTITY_ATTRIBUTE (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4254b-103">IEnumIDENTITY_ATTRIBUTE Interface</span></span>

<span data-ttu-id="4254b-104">Actúa como un enumerador para los atributos del objeto de código en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="4254b-104">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="4254b-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="4254b-105">Methods</span></span>  
  
|<span data-ttu-id="4254b-106">Método</span><span class="sxs-lookup"><span data-stu-id="4254b-106">Method</span></span>|<span data-ttu-id="4254b-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="4254b-107">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="4254b-108">Obtiene un puntero de interfaz a un nuevo `IEnumIDENTITY_ATTRIBUTE` que contiene los mismos miembros que este `IEnumIDENTITY_ATTRIBUTE` .</span><span class="sxs-lookup"><span data-stu-id="4254b-108">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="4254b-109">Escribe los datos contenidos en los elementos de este `IEnumIDENTITY_ATTRIBUTE` en el búfer de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="4254b-109">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="4254b-110">Obtiene el número especificado de atributos, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="4254b-110">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="4254b-111">Mueve el puntero de instrucción al principio de este `IEnumIDENTITY_ATTRIBUTE` .</span><span class="sxs-lookup"><span data-stu-id="4254b-111">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="4254b-112">Mueve el puntero de instrucción hacia delante el número especificado de elementos, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="4254b-112">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="4254b-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4254b-113">Requirements</span></span>  

 <span data-ttu-id="4254b-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4254b-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4254b-115">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="4254b-115">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="4254b-116">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4254b-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4254b-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="4254b-117">See also</span></span>

- [<span data-ttu-id="4254b-118">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="4254b-118">Fusion Interfaces</span></span>](fusion-interfaces.md)
