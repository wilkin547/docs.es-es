---
title: "CorMethodSemanticsAttr (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorMethodSemanticsAttr
api_location: mscoree.dll
api_type: COM
f1_keywords: CorMethodSemanticsAttr
helpviewer_keywords: CorMethodSemanticsAttr enumeration [.NET Framework metadata]
ms.assetid: ca2af325-eb9d-4a91-90e4-267e45b98611
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 09e0c1397a94b75a812e6cbdc52e612a930edae9
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="b68da-102">CorMethodSemanticsAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b68da-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="b68da-103">Contiene valores que describen la relación entre un método y una propiedad o evento asociados.</span><span class="sxs-lookup"><span data-stu-id="b68da-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b68da-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b68da-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="b68da-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b68da-105">Members</span></span>  
  
|<span data-ttu-id="b68da-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b68da-106">Member</span></span>|<span data-ttu-id="b68da-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b68da-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="b68da-108">Especifica que el método es un `set` descriptor de acceso para una propiedad.</span><span class="sxs-lookup"><span data-stu-id="b68da-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="b68da-109">Especifica que el método es un `get` descriptor de acceso para una propiedad.</span><span class="sxs-lookup"><span data-stu-id="b68da-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="b68da-110">Especifica que el método tiene una relación con una propiedad o un evento distintos de los definidos aquí.</span><span class="sxs-lookup"><span data-stu-id="b68da-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="b68da-111">Especifica que el método agrega métodos de controlador de un evento.</span><span class="sxs-lookup"><span data-stu-id="b68da-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="b68da-112">Especifica que el método quita los métodos de control para un evento.</span><span class="sxs-lookup"><span data-stu-id="b68da-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="b68da-113">Especifica que el método genera un evento.</span><span class="sxs-lookup"><span data-stu-id="b68da-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b68da-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b68da-114">Requirements</span></span>  
 <span data-ttu-id="b68da-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b68da-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b68da-116">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="b68da-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="b68da-117">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b68da-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b68da-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="b68da-118">See Also</span></span>  
 [<span data-ttu-id="b68da-119">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="b68da-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
