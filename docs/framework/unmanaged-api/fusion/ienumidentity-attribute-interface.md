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
ms.openlocfilehash: dbb3ac150ebfe9fe3698427d8bb2bfb3e3347c07
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796457"
---
# <a name="ienumidentity_attribute-interface"></a><span data-ttu-id="f921b-102">IEnumIDENTITY_ATTRIBUTE (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f921b-102">IEnumIDENTITY_ATTRIBUTE Interface</span></span>
<span data-ttu-id="f921b-103">Actúa como un enumerador para los atributos del objeto de código en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="f921b-103">Serves as an enumerator for the attributes of the code object in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f921b-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="f921b-104">Methods</span></span>  
  
|<span data-ttu-id="f921b-105">Método</span><span class="sxs-lookup"><span data-stu-id="f921b-105">Method</span></span>|<span data-ttu-id="f921b-106">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="f921b-106">Description</span></span>|  
|------------|-----------------|  
|`IEnumIDENTITY_ATTRIBUTE::Clone`|<span data-ttu-id="f921b-107">Obtiene un puntero de interfaz a un `IEnumIDENTITY_ATTRIBUTE` nuevo que contiene los mismos miembros que `IEnumIDENTITY_ATTRIBUTE`este.</span><span class="sxs-lookup"><span data-stu-id="f921b-107">Gets an interface pointer to a new `IEnumIDENTITY_ATTRIBUTE` that contains the same members as this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::CurrentIntoBuffer`|<span data-ttu-id="f921b-108">Escribe los datos contenidos en los elementos de este `IEnumIDENTITY_ATTRIBUTE` en el búfer de datos especificado.</span><span class="sxs-lookup"><span data-stu-id="f921b-108">Writes the data contained in the elements of this `IEnumIDENTITY_ATTRIBUTE` to the specified data buffer.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Next`|<span data-ttu-id="f921b-109">Obtiene el número especificado de atributos, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="f921b-109">Gets the specified number of attributes, starting at the current position.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Reset`|<span data-ttu-id="f921b-110">Mueve el puntero de instrucción al principio de este `IEnumIDENTITY_ATTRIBUTE`.</span><span class="sxs-lookup"><span data-stu-id="f921b-110">Moves the instruction pointer to the beginning of this `IEnumIDENTITY_ATTRIBUTE`.</span></span>|  
|`IEnumIDENTITY_ATTRIBUTE::Skip`|<span data-ttu-id="f921b-111">Mueve el puntero de instrucción hacia delante el número especificado de elementos, comenzando en la posición actual.</span><span class="sxs-lookup"><span data-stu-id="f921b-111">Moves the instruction pointer forward by the specified number of elements, starting at the current position.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f921b-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f921b-112">Requirements</span></span>  
 <span data-ttu-id="f921b-113">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f921b-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f921b-114">**Encabezado**: Isolation. h</span><span class="sxs-lookup"><span data-stu-id="f921b-114">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="f921b-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f921b-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f921b-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="f921b-116">See also</span></span>

- [<span data-ttu-id="f921b-117">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="f921b-117">Fusion Interfaces</span></span>](fusion-interfaces.md)
