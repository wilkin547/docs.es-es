---
description: 'Más información sobre: enumeración Cormethodsemanticsattr ('
title: CorMethodSemanticsAttr (Enumeración)
ms.date: 03/30/2017
api_name:
- CorMethodSemanticsAttr
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorMethodSemanticsAttr
helpviewer_keywords:
- CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type:
- apiref
ms.openlocfilehash: 4079e81ae2389ff0684fd11d0751b191a7289932
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784371"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="42306-103">CorMethodSemanticsAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="42306-103">CorMethodSemanticsAttr Enumeration</span></span>

<span data-ttu-id="42306-104">Contiene valores que describen la relación entre un método y una propiedad o evento asociados.</span><span class="sxs-lookup"><span data-stu-id="42306-104">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="42306-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="42306-105">Syntax</span></span>  
  
```cpp  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="42306-106">Members</span><span class="sxs-lookup"><span data-stu-id="42306-106">Members</span></span>  
  
|<span data-ttu-id="42306-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="42306-107">Member</span></span>|<span data-ttu-id="42306-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="42306-108">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="42306-109">Especifica que el método es un `set` descriptor de acceso para una propiedad.</span><span class="sxs-lookup"><span data-stu-id="42306-109">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="42306-110">Especifica que el método es un `get` descriptor de acceso para una propiedad.</span><span class="sxs-lookup"><span data-stu-id="42306-110">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="42306-111">Especifica que el método tiene una relación con una propiedad o un evento distintos de los que se definen aquí.</span><span class="sxs-lookup"><span data-stu-id="42306-111">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="42306-112">Especifica que el método agrega métodos de controlador para un evento.</span><span class="sxs-lookup"><span data-stu-id="42306-112">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="42306-113">Especifica que el método quita los métodos de controlador de un evento.</span><span class="sxs-lookup"><span data-stu-id="42306-113">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="42306-114">Especifica que el método genera un evento.</span><span class="sxs-lookup"><span data-stu-id="42306-114">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="42306-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="42306-115">Requirements</span></span>  

 <span data-ttu-id="42306-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="42306-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="42306-117">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="42306-117">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="42306-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="42306-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="42306-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="42306-119">See also</span></span>

- [<span data-ttu-id="42306-120">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="42306-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
