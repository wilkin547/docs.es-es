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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 66d650adb39a9c7dade0936ec671ae5a8b4aeecd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62045479"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="b533d-102">CorNativeLinkType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="b533d-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="b533d-103">Proporciona valores que indican el tipo vinculado en código nativo.</span><span class="sxs-lookup"><span data-stu-id="b533d-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b533d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b533d-104">Syntax</span></span>  
  
```  
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
  
## <a name="members"></a><span data-ttu-id="b533d-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="b533d-105">Members</span></span>  
  
|<span data-ttu-id="b533d-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="b533d-106">Member</span></span>|<span data-ttu-id="b533d-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="b533d-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="b533d-108">Indica que se especifica ninguna de las palabras clave.</span><span class="sxs-lookup"><span data-stu-id="b533d-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="b533d-109">Indica que se especifica una palabra clave ANSI.</span><span class="sxs-lookup"><span data-stu-id="b533d-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="b533d-110">Indica que se especifica una palabra clave de Unicode</span><span class="sxs-lookup"><span data-stu-id="b533d-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="b533d-111">Indica que se especifica una palabra clave auto.</span><span class="sxs-lookup"><span data-stu-id="b533d-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="b533d-112">Indica que se especifica una palabra clave OLE.</span><span class="sxs-lookup"><span data-stu-id="b533d-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="b533d-113">No se utiliza.</span><span class="sxs-lookup"><span data-stu-id="b533d-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b533d-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b533d-114">Requirements</span></span>  
 <span data-ttu-id="b533d-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b533d-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b533d-116">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="b533d-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="b533d-117">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b533d-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="b533d-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b533d-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b533d-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="b533d-119">See also</span></span>

- [<span data-ttu-id="b533d-120">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="b533d-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
