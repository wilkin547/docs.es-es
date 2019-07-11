---
title: COR_FIELD_OFFSET (Estructura)
ms.date: 03/30/2017
api_name:
- COR_FIELD_OFFSET
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- COR_FIELD_OFFSET
helpviewer_keywords:
- COR_FIELD_OFFSET structure [.NET Framework metadata]
ms.assetid: cced5298-277f-4a5a-8ecf-a0050c1096ea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: fdfbb22d231d16be7757ff5df26a5a010928af54
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67767056"
---
# <a name="corfieldoffset-structure"></a><span data-ttu-id="8451a-102">COR_FIELD_OFFSET (Estructura)</span><span class="sxs-lookup"><span data-stu-id="8451a-102">COR_FIELD_OFFSET Structure</span></span>
<span data-ttu-id="8451a-103">Almacena el desplazamiento, dentro de una clase, del campo especificado.</span><span class="sxs-lookup"><span data-stu-id="8451a-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8451a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8451a-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="8451a-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="8451a-105">Members</span></span>  
  
|<span data-ttu-id="8451a-106">Member</span><span class="sxs-lookup"><span data-stu-id="8451a-106">Member</span></span>|<span data-ttu-id="8451a-107">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8451a-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="8451a-108">Un `mdFieldDef` token de metadatos que representa el campo.</span><span class="sxs-lookup"><span data-stu-id="8451a-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="8451a-109">El desplazamiento del campo dentro de su clase.</span><span class="sxs-lookup"><span data-stu-id="8451a-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8451a-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8451a-110">Remarks</span></span>  
 <span data-ttu-id="8451a-111">[GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) y [SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) métodos toman un parámetro de tipo `COR_FIELD_OFFSET`.</span><span class="sxs-lookup"><span data-stu-id="8451a-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8451a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8451a-112">Requirements</span></span>  
 <span data-ttu-id="8451a-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8451a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8451a-114">**Encabezado**: CorHdr.h, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="8451a-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="8451a-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8451a-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8451a-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="8451a-116">See also</span></span>

- [<span data-ttu-id="8451a-117">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="8451a-117">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="8451a-118">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8451a-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="8451a-119">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8451a-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
