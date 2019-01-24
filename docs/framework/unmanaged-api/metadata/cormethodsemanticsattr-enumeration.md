---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f888c39160e52e550d07f58b9c5bcd11fd625658
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54564086"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="5ebf9-102">CorMethodSemanticsAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="5ebf9-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="5ebf9-103">Contiene valores que describen la relación entre un método y una propiedad o evento asociados.</span><span class="sxs-lookup"><span data-stu-id="5ebf9-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ebf9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ebf9-104">Syntax</span></span>  
  
```  
typedef enum CorMethodSemanticsAttr {  
  
    msSetter    =   0x0001,  
    msGetter    =   0x0002,  
    msOther     =   0x0004,  
    msAddOn     =   0x0008,  
    msRemoveOn  =   0x0010,  
    msFire      =   0x0020,  
  
} CorMethodSemanticsAttr;  
```  
  
## <a name="members"></a><span data-ttu-id="5ebf9-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="5ebf9-105">Members</span></span>  
  
|<span data-ttu-id="5ebf9-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="5ebf9-106">Member</span></span>|<span data-ttu-id="5ebf9-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ebf9-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="5ebf9-108">Especifica que el método es un `set` descriptor de acceso para una propiedad.</span><span class="sxs-lookup"><span data-stu-id="5ebf9-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="5ebf9-109">Especifica que el método es un `get` descriptor de acceso para una propiedad.</span><span class="sxs-lookup"><span data-stu-id="5ebf9-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="5ebf9-110">Especifica que el método tiene una relación con una propiedad o un evento distintos de los definidos aquí.</span><span class="sxs-lookup"><span data-stu-id="5ebf9-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="5ebf9-111">Especifica que el método agrega los métodos de controlador de un evento.</span><span class="sxs-lookup"><span data-stu-id="5ebf9-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="5ebf9-112">Especifica que el método quita los métodos de controlador de un evento.</span><span class="sxs-lookup"><span data-stu-id="5ebf9-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="5ebf9-113">Especifica que el método genera un evento.</span><span class="sxs-lookup"><span data-stu-id="5ebf9-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="5ebf9-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5ebf9-114">Requirements</span></span>  
 <span data-ttu-id="5ebf9-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ebf9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ebf9-116">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="5ebf9-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="5ebf9-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ebf9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ebf9-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ebf9-118">See also</span></span>
- [<span data-ttu-id="5ebf9-119">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="5ebf9-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
