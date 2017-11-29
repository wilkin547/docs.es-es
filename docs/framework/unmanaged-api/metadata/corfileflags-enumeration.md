---
title: "CorFileFlags (Enumeración)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorFileFlags
api_location: mscoree.dll
api_type: COM
f1_keywords: CorFileFlags
helpviewer_keywords: CorFileFlags enumeration [.NET Framework metadata]
ms.assetid: d16703fd-518f-412e-92cb-74433d11032e
topic_type: apiref
caps.latest.revision: "7"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: bf123f734f73ecfe726a80099de6ec06b0ced06b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="ac6d6-102">CorFileFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="ac6d6-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="ac6d6-103">Contiene valores que describen el tipo de archivo definido en una llamada a [IMetaDataAssemblyEmit:: DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="ac6d6-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac6d6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac6d6-104">Syntax</span></span>  
  
```  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="ac6d6-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="ac6d6-105">Members</span></span>  
  
|<span data-ttu-id="ac6d6-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="ac6d6-106">Member</span></span>|<span data-ttu-id="ac6d6-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="ac6d6-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="ac6d6-108">Indica que el archivo no es un archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="ac6d6-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="ac6d6-109">Indica que el archivo, posiblemente un archivo de recursos, no contiene metadatos.</span><span class="sxs-lookup"><span data-stu-id="ac6d6-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="ac6d6-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac6d6-110">Requirements</span></span>  
 <span data-ttu-id="ac6d6-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac6d6-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac6d6-112">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="ac6d6-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="ac6d6-113">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac6d6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac6d6-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="ac6d6-114">See Also</span></span>  
 [<span data-ttu-id="ac6d6-115">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="ac6d6-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
