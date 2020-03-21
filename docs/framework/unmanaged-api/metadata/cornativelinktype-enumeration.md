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
ms.openlocfilehash: 0b613ebacdff82a29fdbc3f4caa0f2b8bb5d3f6a
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176167"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="04422-102">CorNativeLinkType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="04422-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="04422-103">Proporciona valores que indican el tipo vinculado en código nativo.</span><span class="sxs-lookup"><span data-stu-id="04422-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="04422-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04422-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="04422-105">Members</span><span class="sxs-lookup"><span data-stu-id="04422-105">Members</span></span>  
  
|<span data-ttu-id="04422-106">Member</span><span class="sxs-lookup"><span data-stu-id="04422-106">Member</span></span>|<span data-ttu-id="04422-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="04422-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="04422-108">Indica que no se especifica ninguna de las palabras clave.</span><span class="sxs-lookup"><span data-stu-id="04422-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="04422-109">Indica que se especifica una palabra clave ANSI.</span><span class="sxs-lookup"><span data-stu-id="04422-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="04422-110">Indica que se especifica una palabra clave Unicode</span><span class="sxs-lookup"><span data-stu-id="04422-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="04422-111">Indica que se especifica una palabra clave auto.</span><span class="sxs-lookup"><span data-stu-id="04422-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="04422-112">Indica que se especifica una palabra clave OLE.</span><span class="sxs-lookup"><span data-stu-id="04422-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="04422-113">No se usa.</span><span class="sxs-lookup"><span data-stu-id="04422-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="04422-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04422-114">Requirements</span></span>  
 <span data-ttu-id="04422-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04422-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04422-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="04422-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="04422-117">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="04422-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="04422-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="04422-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04422-119">Consulte también</span><span class="sxs-lookup"><span data-stu-id="04422-119">See also</span></span>

- [<span data-ttu-id="04422-120">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="04422-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
