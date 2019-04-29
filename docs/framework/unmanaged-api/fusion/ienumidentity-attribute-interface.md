---
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d725228f2a7359d415673fdcb90d0cabae1a40be
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61697347"
---
# <a name="ienumidentityattribute-interface"></a><span data-ttu-id="749df-102">IEnumIDENTITY_ATTRIBUTE (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="749df-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="749df-103">Actúa como un enumerador para los atributos del objeto de código en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="749df-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="749df-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="749df-104">Methods</span></span>  
  
|<span data-ttu-id="749df-105">Método</span><span class="sxs-lookup"><span data-stu-id="749df-105">Method</span></span>|<span data-ttu-id="749df-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="749df-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="749df-107">Obtiene un puntero de interfaz a una nueva `IEnumIDENTITY_ATTRIBUTE` que contiene los mismos miembros que esto `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="749df-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="749df-108">Escribe los datos contenidos en los elementos de este `IEnumIDENTITY_ATTRIBUTE` al búfer de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="749df-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="749df-109">Obtiene el número especificado de atributos, empezando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="749df-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="749df-110">Mueve el puntero de instrucción al principio de este `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="749df-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="749df-111">Mueve el puntero de instrucción al día por el número especificado de elementos, empezando por la posición actual.</span><span class="sxs-lookup"><span data-stu-id="749df-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="749df-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="749df-112">Requirements</span></span>  
 <span data-ttu-id="749df-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="749df-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="749df-114">**Encabezado**: Isolation.h</span><span class="sxs-lookup"><span data-stu-id="749df-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="749df-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="749df-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="749df-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="749df-116">See also</span></span>

- [<span data-ttu-id="749df-117">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="749df-117">Fusion Interfaces</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-interfaces.md)
