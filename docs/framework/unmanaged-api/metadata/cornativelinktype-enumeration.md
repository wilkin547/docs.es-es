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
ms.openlocfilehash: 2bf8848851dc99c60b8c151ed34cd536fa9a8fed
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33443266"
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="f8fa0-102">CorNativeLinkType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="f8fa0-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="f8fa0-103">Proporciona valores que indican el tipo vinculado en código nativo.</span><span class="sxs-lookup"><span data-stu-id="f8fa0-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f8fa0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f8fa0-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="f8fa0-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="f8fa0-105">Members</span></span>  
  
|<span data-ttu-id="f8fa0-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="f8fa0-106">Member</span></span>|<span data-ttu-id="f8fa0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="f8fa0-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="f8fa0-108">Indica que no se especifica ninguna de las palabras clave.</span><span class="sxs-lookup"><span data-stu-id="f8fa0-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="f8fa0-109">Indica que se ha especificado una palabra clave ANSI.</span><span class="sxs-lookup"><span data-stu-id="f8fa0-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="f8fa0-110">Indica que se ha especificado una palabra clave Unicode</span><span class="sxs-lookup"><span data-stu-id="f8fa0-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="f8fa0-111">Indica que se ha especificado una palabra clave auto.</span><span class="sxs-lookup"><span data-stu-id="f8fa0-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="f8fa0-112">Indica que se ha especificado una palabra clave OLE.</span><span class="sxs-lookup"><span data-stu-id="f8fa0-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="f8fa0-113">No usado.</span><span class="sxs-lookup"><span data-stu-id="f8fa0-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f8fa0-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f8fa0-114">Requirements</span></span>  
 <span data-ttu-id="f8fa0-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f8fa0-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f8fa0-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="f8fa0-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f8fa0-117">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="f8fa0-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f8fa0-118">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f8fa0-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f8fa0-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="f8fa0-119">See Also</span></span>  
 [<span data-ttu-id="f8fa0-120">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="f8fa0-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
