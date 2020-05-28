---
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
ms.openlocfilehash: 29f2401e2e3faccae05ca5249fcd7d9e89aacb46
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007616"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="d6c79-102">CorNativeLinkType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="d6c79-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="d6c79-103">Proporciona valores que indican el tipo vinculado en código nativo.</span><span class="sxs-lookup"><span data-stu-id="d6c79-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d6c79-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d6c79-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="d6c79-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="d6c79-105">Members</span></span>  
  
|<span data-ttu-id="d6c79-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="d6c79-106">Member</span></span>|<span data-ttu-id="d6c79-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="d6c79-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="d6c79-108">Indica que no se ha especificado ninguna de las palabras clave.</span><span class="sxs-lookup"><span data-stu-id="d6c79-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="d6c79-109">Indica que se ha especificado una palabra clave ANSI.</span><span class="sxs-lookup"><span data-stu-id="d6c79-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="d6c79-110">Indica que se ha especificado una palabra clave de Unicode</span><span class="sxs-lookup"><span data-stu-id="d6c79-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="d6c79-111">Indica que se ha especificado una palabra clave auto.</span><span class="sxs-lookup"><span data-stu-id="d6c79-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="d6c79-112">Indica que se ha especificado una palabra clave OLE.</span><span class="sxs-lookup"><span data-stu-id="d6c79-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="d6c79-113">No se usa.</span><span class="sxs-lookup"><span data-stu-id="d6c79-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="d6c79-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d6c79-114">Requirements</span></span>  
 <span data-ttu-id="d6c79-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d6c79-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d6c79-116">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="d6c79-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d6c79-117">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d6c79-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d6c79-118">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d6c79-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d6c79-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d6c79-119">See also</span></span>

- [<span data-ttu-id="d6c79-120">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="d6c79-120">Metadata Enumerations</span></span>](metadata-enumerations.md)
