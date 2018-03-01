---
title: "CorErrorIfEmitOutOfOrder (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- CorErrorIfEmitOutOfOrder
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorErrorIfEmitOutOfOrder
helpviewer_keywords:
- CorErrorIfEmitOutOfOrder enumeration [.NET Framework metadata]
ms.assetid: 6d758aad-29a7-44fe-9481-bbff5b799a32
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7c049d78d8ba67ec5f08fc2beb584fef4987c9e8
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="90d0c-102">CorErrorIfEmitOutOfOrder (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="90d0c-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>
<span data-ttu-id="90d0c-103">Contiene valores de marca que indican las condiciones en las que se debe generar un mensaje de error cuando los metadatos se emiten sin orden.</span><span class="sxs-lookup"><span data-stu-id="90d0c-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="90d0c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="90d0c-104">Syntax</span></span>  
  
```  
typedef enum CorErrorIfEmitOutOfOrder {  
  
    MDErrorOutOfOrderDefault    = 0x00000000,  
    MDErrorOutOfOrderNone       = 0x00000000,  
    MDErrorOutOfOrderAll        = 0xffffffff,  
    MDMethodOutOfOrder          = 0x00000001,  
    MDFieldOutOfOrder           = 0x00000002,  
    MDParamOutOfOrder           = 0x00000004,  
    MDPropertyOutOfOrder        = 0x00000008,  
    MDEventOutOfOrder           = 0x00000010  
  
} CorErrorIfEmitOutOfOrder;  
```  
  
## <a name="members"></a><span data-ttu-id="90d0c-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="90d0c-105">Members</span></span>  
  
|<span data-ttu-id="90d0c-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="90d0c-106">Member</span></span>|<span data-ttu-id="90d0c-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="90d0c-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="90d0c-108">Indica el comportamiento predeterminado, que no generan mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="90d0c-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="90d0c-109">Indica que el compilador no debe generar mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="90d0c-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="90d0c-110">Indica que el compilador debe generar un mensaje de error cuando un campo, propiedad, evento, método o parámetro se emite sin orden.</span><span class="sxs-lookup"><span data-stu-id="90d0c-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="90d0c-111">Indica que el compilador debe generar un mensaje de error cuando un método no se emite en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="90d0c-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="90d0c-112">Indica que el compilador debe generar un mensaje de error cuando un campo no se emite en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="90d0c-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="90d0c-113">Indica que el compilador debe generar un mensaje de error cuando un parámetro no se emite en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="90d0c-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="90d0c-114">Indica que el compilador debe generar un mensaje de error cuando una propiedad se emite sin orden.</span><span class="sxs-lookup"><span data-stu-id="90d0c-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="90d0c-115">Indica que el compilador debe generar un mensaje de error cuando se genera un evento fuera de servicio.</span><span class="sxs-lookup"><span data-stu-id="90d0c-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="90d0c-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="90d0c-116">Requirements</span></span>  
 <span data-ttu-id="90d0c-117">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="90d0c-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="90d0c-118">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="90d0c-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="90d0c-119">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="90d0c-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="90d0c-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="90d0c-120">See Also</span></span>  
 [<span data-ttu-id="90d0c-121">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="90d0c-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
