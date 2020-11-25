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
ms.openlocfilehash: 71a6ea9f593da093985a4420e690f1bdd7f9d139
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95728997"
---
# <a name="ienumidentity_attribute-interface"></a><span data-ttu-id="e88ca-102">IEnumIDENTITY_ATTRIBUTE (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e88ca-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>

<span data-ttu-id="e88ca-103">Actúa como un enumerador para los atributos del objeto de código en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="e88ca-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="e88ca-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="e88ca-104">Methods</span></span>  
  
|<span data-ttu-id="e88ca-105">Método</span><span class="sxs-lookup"><span data-stu-id="e88ca-105">Method</span></span>|<span data-ttu-id="e88ca-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="e88ca-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="e88ca-107">Obtiene un puntero de interfaz a un nuevo `IEnumIDENTITY_ATTRIBUTE` que contiene los mismos miembros que este `IEnumIDENTITY_ATTRIBUTE` .</span><span class="sxs-lookup"><span data-stu-id="e88ca-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="e88ca-108">Escribe los datos contenidos en los elementos de este `IEnumIDENTITY_ATTRIBUTE` en el búfer de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="e88ca-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="e88ca-109">Obtiene el número especificado de atributos, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="e88ca-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="e88ca-110">Mueve el puntero de instrucción al principio de este `IEnumIDENTITY_ATTRIBUTE` .</span><span class="sxs-lookup"><span data-stu-id="e88ca-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="e88ca-111">Mueve el puntero de instrucción hacia delante el número especificado de elementos, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="e88ca-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="e88ca-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e88ca-112">Requirements</span></span>  

 <span data-ttu-id="e88ca-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e88ca-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e88ca-114">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="e88ca-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="e88ca-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="e88ca-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e88ca-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e88ca-116">See also</span></span>

- [<span data-ttu-id="e88ca-117">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="e88ca-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
