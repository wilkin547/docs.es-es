---
title: CorErrorIfEmitOutOfOrder (Enumeración)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 16f6d7bf6fa1730d50cfe81526817e492a453dad
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781984"
---
# <a name="corerrorifemitoutoforder-enumeration"></a><span data-ttu-id="7fb7f-102">CorErrorIfEmitOutOfOrder (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="7fb7f-102">CorErrorIfEmitOutOfOrder Enumeration</span></span>
<span data-ttu-id="7fb7f-103">Contiene valores de marca que indican las condiciones en las que se debe generar un mensaje de error cuando los metadatos se emiten sin orden.</span><span class="sxs-lookup"><span data-stu-id="7fb7f-103">Contains flag values that indicate the conditions under which an error message should be generated when metadata is emitted out of order.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7fb7f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7fb7f-104">Syntax</span></span>  
  
```cpp  
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
  
## <a name="members"></a><span data-ttu-id="7fb7f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="7fb7f-105">Members</span></span>  
  
|<span data-ttu-id="7fb7f-106">Member</span><span class="sxs-lookup"><span data-stu-id="7fb7f-106">Member</span></span>|<span data-ttu-id="7fb7f-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="7fb7f-107">Description</span></span>|  
|------------|-----------------|  
|`MDErrorOutOfOrderDefault`|<span data-ttu-id="7fb7f-108">Indica el comportamiento predeterminado, que no generan mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="7fb7f-108">Indicates the default behavior, which does not generate error messages.</span></span>|  
|`MDErrorOutOfOrderNone`|<span data-ttu-id="7fb7f-109">Indica que el compilador no debe generar mensajes de error.</span><span class="sxs-lookup"><span data-stu-id="7fb7f-109">Indicates that the compiler should not generate error messages.</span></span>|  
|`MDErrorOutOfOrderAll`|<span data-ttu-id="7fb7f-110">Indica que el compilador debe generar un mensaje de error cuando un campo, propiedad, evento, método o parámetro que se emite sin orden.</span><span class="sxs-lookup"><span data-stu-id="7fb7f-110">Indicates that the compiler should generate an error message when a field, property, event, method, or parameter is emitted out of order.</span></span>|  
|`MDMethodOutOfOrder`|<span data-ttu-id="7fb7f-111">Indica que el compilador debe generar un mensaje de error cuando un método que se emite sin orden.</span><span class="sxs-lookup"><span data-stu-id="7fb7f-111">Indicates that the compiler should generate an error message when a method is emitted out of order.</span></span>|  
|`MDFieldOutOfOrder`|<span data-ttu-id="7fb7f-112">Indica que el compilador debe generar un mensaje de error cuando un campo se emite sin orden.</span><span class="sxs-lookup"><span data-stu-id="7fb7f-112">Indicates that the compiler should generate an error message when a field is emitted out of order.</span></span>|  
|`MDParamOutOfOrder`|<span data-ttu-id="7fb7f-113">Indica que el compilador debe generar un mensaje de error cuando un parámetro que se emite sin orden.</span><span class="sxs-lookup"><span data-stu-id="7fb7f-113">Indicates that the compiler should generate an error message when a parameter is emitted out of order.</span></span>|  
|`MDPropertyOutOfOrder`|<span data-ttu-id="7fb7f-114">Indica que el compilador debe generar un mensaje de error cuando una propiedad se emite sin orden.</span><span class="sxs-lookup"><span data-stu-id="7fb7f-114">Indicates that the compiler should generate an error message when a property is emitted out of order.</span></span>|  
|`MDEventOutOfOrder`|<span data-ttu-id="7fb7f-115">Indica que el compilador debe generar un mensaje de error cuando se emite un evento en el orden correcto.</span><span class="sxs-lookup"><span data-stu-id="7fb7f-115">Indicates that the compiler should generate an error message when an event is emitted out of order.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7fb7f-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7fb7f-116">Requirements</span></span>  
 <span data-ttu-id="7fb7f-117">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7fb7f-117">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7fb7f-118">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="7fb7f-118">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="7fb7f-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7fb7f-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7fb7f-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="7fb7f-120">See also</span></span>

- [<span data-ttu-id="7fb7f-121">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="7fb7f-121">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
