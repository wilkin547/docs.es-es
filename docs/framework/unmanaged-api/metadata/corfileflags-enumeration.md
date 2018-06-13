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
ms.openlocfilehash: 7ecc2f62a6bb8119b7fe06a82aea827a58d04ecb
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33441673"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="819c0-102">CorFileFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="819c0-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="819c0-103">Contiene valores que describen el tipo de archivo definido en una llamada a [IMetaDataAssemblyEmit:: DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="819c0-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="819c0-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="819c0-104">Syntax</span></span>  
  
```  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="819c0-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="819c0-105">Members</span></span>  
  
|<span data-ttu-id="819c0-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="819c0-106">Member</span></span>|<span data-ttu-id="819c0-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="819c0-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="819c0-108">Indica que el archivo no es un archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="819c0-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="819c0-109">Indica que el archivo, posiblemente un archivo de recursos, no contiene metadatos.</span><span class="sxs-lookup"><span data-stu-id="819c0-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="819c0-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="819c0-110">Requirements</span></span>  
 <span data-ttu-id="819c0-111">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="819c0-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="819c0-112">**Encabezado:** CorHdr.h</span><span class="sxs-lookup"><span data-stu-id="819c0-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="819c0-113">**Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="819c0-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="819c0-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="819c0-114">See Also</span></span>  
 [<span data-ttu-id="819c0-115">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="819c0-115">Metadata Enumerations</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
