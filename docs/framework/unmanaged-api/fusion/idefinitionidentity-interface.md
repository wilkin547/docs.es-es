---
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
ms.openlocfilehash: 59578e1d3a66809c86f7daad1b208df2ae09568d
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73108040"
---
# <a name="idefinitionidentity-interface"></a><span data-ttu-id="47bf8-102">IDefinitionIdentity (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="47bf8-102">IDefinitionIdentity Interface</span></span>
<span data-ttu-id="47bf8-103">Representa la firma única del código que define la aplicación en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="47bf8-103">Represents the unique signature of the code that defines the application in the current scope.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="47bf8-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="47bf8-104">Methods</span></span>  
  
|<span data-ttu-id="47bf8-105">Método</span><span class="sxs-lookup"><span data-stu-id="47bf8-105">Method</span></span>|<span data-ttu-id="47bf8-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="47bf8-106">Description</span></span>|  
|------------|-----------------|  
|`IDefinitionIdentity::Clone`|<span data-ttu-id="47bf8-107">Obtiene un puntero de interfaz a un nuevo objeto `IDefinitionIdentity` que es idéntico a este `IDefinitionIdentity`, excepto por los cambios de atributo especificados.</span><span class="sxs-lookup"><span data-stu-id="47bf8-107">Gets an interface pointer to a new `IDefinitionIdentity` object that is identical to this `IDefinitionIdentity`, except for the specified attribute changes.</span></span>|  
|`IDefinitionIdentity::EnumAttributes`|<span data-ttu-id="47bf8-108">Obtiene un puntero de interfaz a un objeto [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) que contiene los atributos asociados a este `IDefinitionIdentity`.</span><span class="sxs-lookup"><span data-stu-id="47bf8-108">Gets an interface pointer to an [IEnumIDENTITY_ATTRIBUTE](ienumidentity-attribute-interface.md) object that contains the attributes associated with this `IDefinitionIdentity`.</span></span>|  
|`IDefinitionIdentity::GetAttribute`|<span data-ttu-id="47bf8-109">Obtiene el valor del atributo con el nombre especificado en el espacio de nombres especificado.</span><span class="sxs-lookup"><span data-stu-id="47bf8-109">Gets the value of the attribute with the specified name in the specified namespace.</span></span>|  
|`IDefinitionIdentity::SetAttribute`|<span data-ttu-id="47bf8-110">Establece el atributo que tiene el nombre especificado en el espacio de nombres especificado en el valor especificado.</span><span class="sxs-lookup"><span data-stu-id="47bf8-110">Sets the attribute that has the specified name in the specified namespace to the specified value.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="47bf8-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47bf8-111">Requirements</span></span>  
 <span data-ttu-id="47bf8-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47bf8-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47bf8-113">**Encabezado:** Isolation. h</span><span class="sxs-lookup"><span data-stu-id="47bf8-113">**Header:** Isolation.h</span></span>  
  
 <span data-ttu-id="47bf8-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="47bf8-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47bf8-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="47bf8-115">See also</span></span>

- [<span data-ttu-id="47bf8-116">Interfaces de Fusion</span><span class="sxs-lookup"><span data-stu-id="47bf8-116">Fusion Interfaces</span></span>](fusion-interfaces.md)
