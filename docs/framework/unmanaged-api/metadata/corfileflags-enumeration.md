---
description: 'Más información sobre: enumeración CorFileFlags ('
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
ms.openlocfilehash: 8ffad9bad9c656a10c2c556f5e06f9d510ccb45a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99784488"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="cfadf-103">CorFileFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="cfadf-103">CorFileFlags Enumeration</span></span>

<span data-ttu-id="cfadf-104">Contiene valores que describen el tipo de archivo definido en una llamada a [IMetaDataAssemblyEmit::D efinefile](imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="cfadf-104">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cfadf-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cfadf-105">Syntax</span></span>  
  
```cpp  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="cfadf-106">Members</span><span class="sxs-lookup"><span data-stu-id="cfadf-106">Members</span></span>  
  
|<span data-ttu-id="cfadf-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="cfadf-107">Member</span></span>|<span data-ttu-id="cfadf-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="cfadf-108">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="cfadf-109">Indica que el archivo no es un archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="cfadf-109">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="cfadf-110">Indica que el archivo, posiblemente un archivo de recursos, no contiene metadatos.</span><span class="sxs-lookup"><span data-stu-id="cfadf-110">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="cfadf-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cfadf-111">Requirements</span></span>  

 <span data-ttu-id="cfadf-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cfadf-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cfadf-113">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="cfadf-113">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="cfadf-114">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cfadf-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfadf-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cfadf-115">See also</span></span>

- [<span data-ttu-id="cfadf-116">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="cfadf-116">Metadata Enumerations</span></span>](metadata-enumerations.md)
