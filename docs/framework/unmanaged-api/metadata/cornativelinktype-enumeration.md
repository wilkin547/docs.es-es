---
description: 'Más información sobre: enumeración Cornativelinktype ('
title: CorNativeLinkType (Enumeración)
ms.date: 03/30/2017
api_name:
- CorNativeLinkType
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorNativeLinkType
helpviewer_keywords:
- CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type:
- apiref
ms.openlocfilehash: 40efc75a793da8b024eff3d7c2c620123eca08b2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784345"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="c8f79-103">CorNativeLinkType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="c8f79-103">CorNativeLinkType Enumeration</span></span>

<span data-ttu-id="c8f79-104">Proporciona valores que indican el tipo vinculado en código nativo.</span><span class="sxs-lookup"><span data-stu-id="c8f79-104">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c8f79-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c8f79-105">Syntax</span></span>  
  
```cpp  
typedef enum
{  
    nltNone       = 1,  
    nltAnsi       = 2,  
    nltUnicode    = 3,  
    nltAuto       = 4,  
    nltOle        = 5,  
    nltMaxValue   = 7  
} CorNativeLinkType;  
```  
  
## <a name="members"></a><span data-ttu-id="c8f79-106">Members</span><span class="sxs-lookup"><span data-stu-id="c8f79-106">Members</span></span>  
  
|<span data-ttu-id="c8f79-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="c8f79-107">Member</span></span>|<span data-ttu-id="c8f79-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="c8f79-108">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="c8f79-109">Indica que no se ha especificado ninguna de las palabras clave.</span><span class="sxs-lookup"><span data-stu-id="c8f79-109">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="c8f79-110">Indica que se ha especificado una palabra clave ANSI.</span><span class="sxs-lookup"><span data-stu-id="c8f79-110">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="c8f79-111">Indica que se ha especificado una palabra clave de Unicode</span><span class="sxs-lookup"><span data-stu-id="c8f79-111">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="c8f79-112">Indica que se ha especificado una palabra clave auto.</span><span class="sxs-lookup"><span data-stu-id="c8f79-112">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="c8f79-113">Indica que se ha especificado una palabra clave OLE.</span><span class="sxs-lookup"><span data-stu-id="c8f79-113">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="c8f79-114">No se usa.</span><span class="sxs-lookup"><span data-stu-id="c8f79-114">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c8f79-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c8f79-115">Requirements</span></span>  

 <span data-ttu-id="c8f79-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c8f79-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c8f79-117">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c8f79-117">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c8f79-118">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c8f79-118">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c8f79-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c8f79-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8f79-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="c8f79-120">See also</span></span>

- [<span data-ttu-id="c8f79-121">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="c8f79-121">Metadata Enumerations</span></span>](metadata-enumerations.md)
