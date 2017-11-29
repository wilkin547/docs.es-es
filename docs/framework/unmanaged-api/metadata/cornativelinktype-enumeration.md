---
title: "CorNativeLinkType (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorNativeLinkType
api_location: mscoree.dll
api_type: COM
f1_keywords: CorNativeLinkType
helpviewer_keywords: CorNativeLinkType enumeration [.NET Framework metadata]
ms.assetid: 4f86ff37-2dab-4e64-819a-76b3bfe828ff
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: b8da034590bc5e0b2cbd9456d9d5b4ef4970f259
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="cornativelinktype-enumeration"></a><span data-ttu-id="2e55f-102">CorNativeLinkType (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="2e55f-102">CorNativeLinkType Enumeration</span></span>
<span data-ttu-id="2e55f-103">Proporciona valores que indican el tipo vinculado en código nativo.</span><span class="sxs-lookup"><span data-stu-id="2e55f-103">Provides values that indicate the type linked in native code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2e55f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2e55f-104">Syntax</span></span>  
  
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
  
## <a name="members"></a><span data-ttu-id="2e55f-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="2e55f-105">Members</span></span>  
  
|<span data-ttu-id="2e55f-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="2e55f-106">Member</span></span>|<span data-ttu-id="2e55f-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="2e55f-107">Description</span></span>|  
|------------|-----------------|  
|`nltNone`|<span data-ttu-id="2e55f-108">Indica que no se especifica ninguna de las palabras clave.</span><span class="sxs-lookup"><span data-stu-id="2e55f-108">Indicates that none of the keywords are specified.</span></span>|  
|`nltAnsi`|<span data-ttu-id="2e55f-109">Indica que se ha especificado una palabra clave ANSI.</span><span class="sxs-lookup"><span data-stu-id="2e55f-109">Indicates that an ANSI keyword is specified.</span></span>|  
|`nltUnicode`|<span data-ttu-id="2e55f-110">Indica que se ha especificado una palabra clave Unicode</span><span class="sxs-lookup"><span data-stu-id="2e55f-110">Indicates that a Unicode keyword is specified</span></span>|  
|`nltAuto`|<span data-ttu-id="2e55f-111">Indica que se ha especificado una palabra clave auto.</span><span class="sxs-lookup"><span data-stu-id="2e55f-111">Indicates that an auto keyword is specified.</span></span>|  
|`nltOle`|<span data-ttu-id="2e55f-112">Indica que se ha especificado una palabra clave OLE.</span><span class="sxs-lookup"><span data-stu-id="2e55f-112">Indicates that an OLE keyword is specified.</span></span>|  
|`nltMaxValue`|<span data-ttu-id="2e55f-113">No usado.</span><span class="sxs-lookup"><span data-stu-id="2e55f-113">Not used.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2e55f-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2e55f-114">Requirements</span></span>  
 <span data-ttu-id="2e55f-115">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2e55f-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2e55f-116">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2e55f-116">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2e55f-117">**Biblioteca:** incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2e55f-117">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2e55f-118">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2e55f-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2e55f-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="2e55f-119">See Also</span></span>  
 [<span data-ttu-id="2e55f-120">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="2e55f-120">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
