---
title: "CorSaveSize (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorSaveSize
api_location: mscoree.dll
api_type: COM
f1_keywords: CorSaveSize
helpviewer_keywords: CorSaveSize enumeration [.NET Framework metadata]
ms.assetid: eb95ce39-5688-43c1-a34d-578794b32faa
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 3780050285f63fa7334ec5463cd22050836dc136
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="corsavesize-enumeration"></a><span data-ttu-id="27383-102">CorSaveSize (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="27383-102">CorSaveSize Enumeration</span></span>
<span data-ttu-id="27383-103">Contiene valores que indican el nivel de precisión necesario al consultar el tamaño de una operación de guardar.</span><span class="sxs-lookup"><span data-stu-id="27383-103">Contains values indicating the level of precision required when querying for the size of a save operation.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="27383-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="27383-104">Syntax</span></span>  
  
```  
typedef enum CorSaveSize {  
    cssAccurate                = 0x0000,   
    cssQuick                   = 0x0001,   
    cssDiscardTransientCAs     = 0x0002  
} CorSaveSize;  
```  
  
## <a name="members"></a><span data-ttu-id="27383-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="27383-105">Members</span></span>  
  
|<span data-ttu-id="27383-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="27383-106">Member</span></span>|<span data-ttu-id="27383-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="27383-107">Description</span></span>|  
|------------|-----------------|  
|`cssAccurate`|<span data-ttu-id="27383-108">Especifica que el valor devuelto debe ser exacto.</span><span class="sxs-lookup"><span data-stu-id="27383-108">Specifies that the return value should be exact.</span></span>|  
|`cssQuick`|<span data-ttu-id="27383-109">Especifica que se debería estimar el valor devuelto.</span><span class="sxs-lookup"><span data-stu-id="27383-109">Specifies that the return value should be estimated.</span></span>|  
|`cssDiscardTransientCAs`|<span data-ttu-id="27383-110">Especifica que se deben quitar los tipos descartables.</span><span class="sxs-lookup"><span data-stu-id="27383-110">Specifies that discardable types should be removed.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="27383-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="27383-111">Requirements</span></span>  
 <span data-ttu-id="27383-112">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="27383-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="27383-113">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="27383-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="27383-114">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="27383-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="27383-115">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="27383-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27383-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="27383-116">See Also</span></span>  
 [<span data-ttu-id="27383-117">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="27383-117">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
