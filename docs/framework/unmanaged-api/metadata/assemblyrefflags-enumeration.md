---
title: "AssemblyRefFlags (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: AssemblyRefFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: AssemblyRefFlags
helpviewer_keywords: AssemblyRefFlags enumeration [.NET Framework metadata]
ms.assetid: decd4f46-f3b2-466f-9501-e74f2b86b846
topic_type: apiref
caps.latest.revision: "8"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: fc64d03725df89eac91c85549e287eeb2510037c
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="assemblyrefflags-enumeration"></a><span data-ttu-id="baf64-102">AssemblyRefFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="baf64-102">AssemblyRefFlags Enumeration</span></span>
<span data-ttu-id="baf64-103">Contiene valores que describen las características de una referencia de ensamblado.</span><span class="sxs-lookup"><span data-stu-id="baf64-103">Contains values that describe features of an assembly reference.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="baf64-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="baf64-104">Syntax</span></span>  
  
```  
typedef enum {  
    arfFullOriginator = 0x0001  
} AssemblyRefFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="baf64-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="baf64-105">Members</span></span>  
  
|<span data-ttu-id="baf64-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="baf64-106">Member</span></span>|<span data-ttu-id="baf64-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="baf64-107">Description</span></span>|  
|------------|-----------------|  
|`arfFullOriginator`|<span data-ttu-id="baf64-108">Especifica que la referencia de ensamblado contiene información completa, sin valor de hash sobre el publicador del ensamblado.</span><span class="sxs-lookup"><span data-stu-id="baf64-108">Specifies that the assembly reference contains full, unhashed information about the publisher of the assembly.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="baf64-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="baf64-109">Requirements</span></span>  
 <span data-ttu-id="baf64-110">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="baf64-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="baf64-111">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="baf64-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="baf64-112">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="baf64-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="baf64-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="baf64-113">See Also</span></span>  
 [<span data-ttu-id="baf64-114">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="baf64-114">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)  
 [<span data-ttu-id="baf64-115">IMetaDataAssemblyEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="baf64-115">IMetaDataAssemblyEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-interface.md)  
 [<span data-ttu-id="baf64-116">DefineAssemblyRef (método)</span><span class="sxs-lookup"><span data-stu-id="baf64-116">DefineAssemblyRef Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-defineassemblyref-method.md)
