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
ms.openlocfilehash: de467c98dfa7ad3eac69502f2afe311b301e1ec5
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33444814"
---
# <a name="cormethodsemanticsattr-enumeration"></a><span data-ttu-id="855af-102">CorMethodSemanticsAttr (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="855af-102">CorMethodSemanticsAttr Enumeration</span></span>
<span data-ttu-id="855af-103">Contiene valores que describen la relación entre un método y una propiedad o evento asociados.</span><span class="sxs-lookup"><span data-stu-id="855af-103">Contains values that describe the relationship between a method and an associated property or event.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="855af-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="855af-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="855af-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="855af-105">Members</span></span>  
  
|<span data-ttu-id="855af-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="855af-106">Member</span></span>|<span data-ttu-id="855af-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="855af-107">Description</span></span>|  
|------------|-----------------|  
|`msSetter`|<span data-ttu-id="855af-108">Especifica que el método es un `set` descriptor de acceso para una propiedad.</span><span class="sxs-lookup"><span data-stu-id="855af-108">Specifies that the method is a `set` accessor for a property.</span></span>|  
|`msGetter`|<span data-ttu-id="855af-109">Especifica que el método es un `get` descriptor de acceso para una propiedad.</span><span class="sxs-lookup"><span data-stu-id="855af-109">Specifies that the method is a `get` accessor for a property.</span></span>|  
|`msOther`|<span data-ttu-id="855af-110">Especifica que el método tiene una relación con una propiedad o un evento distintos de los definidos aquí.</span><span class="sxs-lookup"><span data-stu-id="855af-110">Specifies that the method has a relationship to a property or an event other than those defined here.</span></span>|  
|`msAddOn`|<span data-ttu-id="855af-111">Especifica que el método agrega métodos de controlador de un evento.</span><span class="sxs-lookup"><span data-stu-id="855af-111">Specifies that the method adds handler methods for an event.</span></span>|  
|`msRemoveOn`|<span data-ttu-id="855af-112">Especifica que el método quita los métodos de control para un evento.</span><span class="sxs-lookup"><span data-stu-id="855af-112">Specifies that the method removes handler methods for an event.</span></span>|  
|`msFire`|<span data-ttu-id="855af-113">Especifica que el método genera un evento.</span><span class="sxs-lookup"><span data-stu-id="855af-113">Specifies that the method raises an event.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="855af-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="855af-114">Requirements</span></span>  
 <span data-ttu-id="855af-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="855af-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="855af-116">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="855af-116">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="855af-117">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="855af-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="855af-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="855af-118">See Also</span></span>  
 [<span data-ttu-id="855af-119">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="855af-119">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
