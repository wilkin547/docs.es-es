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
ms.openlocfilehash: c8c2757e99b80204ad52e69a596d62c55c369965
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007421"
---
# <a name="corfileflags-enumeration"></a><span data-ttu-id="38a29-102">CorFileFlags (Enumeración)</span><span class="sxs-lookup"><span data-stu-id="38a29-102">CorFileFlags Enumeration</span></span>
<span data-ttu-id="38a29-103">Contiene valores que describen el tipo de archivo definido en una llamada a [IMetaDataAssemblyEmit::D efinefile](imetadataassemblyemit-definefile-method.md).</span><span class="sxs-lookup"><span data-stu-id="38a29-103">Contains values that describe the type of file defined in a call to [IMetaDataAssemblyEmit::DefineFile](imetadataassemblyemit-definefile-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38a29-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="38a29-104">Syntax</span></span>  
  
```cpp  
typedef enum CorFileFlags {  
  
    ffContainsMetaData      =   0x0000,  
    ffContainsNoMetaData    =   0x0001  
  
} CorFileFlags;  
```  
  
## <a name="members"></a><span data-ttu-id="38a29-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="38a29-105">Members</span></span>  
  
|<span data-ttu-id="38a29-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="38a29-106">Member</span></span>|<span data-ttu-id="38a29-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="38a29-107">Description</span></span>|  
|------------|-----------------|  
|`ffContainsMetaData`|<span data-ttu-id="38a29-108">Indica que el archivo no es un archivo de recursos.</span><span class="sxs-lookup"><span data-stu-id="38a29-108">Indicates that the file is not a resource file.</span></span>|  
|`ffContainsNoMetaData`|<span data-ttu-id="38a29-109">Indica que el archivo, posiblemente un archivo de recursos, no contiene metadatos.</span><span class="sxs-lookup"><span data-stu-id="38a29-109">Indicates that the file, possibly a resource file, does not contain metadata.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38a29-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="38a29-110">Requirements</span></span>  
 <span data-ttu-id="38a29-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="38a29-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38a29-112">**Encabezado:** CorHdr. h</span><span class="sxs-lookup"><span data-stu-id="38a29-112">**Header:** CorHdr.h</span></span>  
  
 <span data-ttu-id="38a29-113">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38a29-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38a29-114">Consulte también</span><span class="sxs-lookup"><span data-stu-id="38a29-114">See also</span></span>

- [<span data-ttu-id="38a29-115">Enumeraciones para metadatos</span><span class="sxs-lookup"><span data-stu-id="38a29-115">Metadata Enumerations</span></span>](metadata-enumerations.md)
