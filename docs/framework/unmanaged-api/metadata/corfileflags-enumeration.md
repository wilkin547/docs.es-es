---
title: CorFileFlags (Enumeración)
ms.date: 03/30/2017
api_name:
- CorFileFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorFileFlags
helpviewer_keywords:
- CorFileFlags enumeration [.NET Framework metadata]
ms.assetid: d16703fd-518f-412e-92cb-74433d11032e
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8a614ad1bd9738c993775667ccd261a089e8b57a
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624268"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="09984-102">CorFileFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="09984-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="09984-103">Contiene valores que describen el tipo de archivo definido en una llamada a [IMetaDataAssemblyEmit:: DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="09984-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="09984-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="09984-104">Syntax</span></span>  
  
```  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="09984-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="09984-105">Members</span></span>  
  
|<span data-ttu-id="09984-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="09984-106">Member</span></span>|<span data-ttu-id="09984-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="09984-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="09984-108">Indica que el archivo no es un archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="09984-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="09984-109">Indica que el archivo, posiblemente un archivo de recursos, no contiene metadatos.</span><span class="sxs-lookup"><span data-stu-id="09984-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="09984-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="09984-110">Requirements</span></span>  
 <span data-ttu-id="09984-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="09984-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="09984-112">**Encabezado**: CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="09984-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="09984-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="09984-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="09984-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="09984-114">See also</span></span>
- [<span data-ttu-id="09984-115">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="09984-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
