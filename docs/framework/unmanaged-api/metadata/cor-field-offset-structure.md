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
ms.openlocfilehash: 70fb637cd1edf81be140b0e3306e3b0a483653a6
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007993"
---
# <a name="cor_field_offset-structure"></a><span data-ttu-id="877bc-102">COR_FIELD_OFFSET (Estructura)</span><span class="sxs-lookup"><span data-stu-id="877bc-102">COR_FIELD_OFFSET Structure</span></span>
<span data-ttu-id="877bc-103">Almacena el desplazamiento, dentro de una clase, del campo especificado.</span><span class="sxs-lookup"><span data-stu-id="877bc-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="877bc-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="877bc-104">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="877bc-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="877bc-105">Members</span></span>  
  
|<span data-ttu-id="877bc-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="877bc-106">Member</span></span>|<span data-ttu-id="877bc-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="877bc-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="877bc-108">`mdFieldDef`Token de metadatos que representa el campo.</span><span class="sxs-lookup"><span data-stu-id="877bc-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="877bc-109">Desplazamiento del campo dentro de su clase.</span><span class="sxs-lookup"><span data-stu-id="877bc-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="877bc-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="877bc-110">Remarks</span></span>  
 <span data-ttu-id="877bc-111">Los métodos [IMetaDataImport:: GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) y [IMetaDataEmit:: setclasslayout (](imetadataemit-setclasslayout-method.md) toman un parámetro de tipo `COR_FIELD_OFFSET` .</span><span class="sxs-lookup"><span data-stu-id="877bc-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="877bc-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="877bc-112">Requirements</span></span>  
 <span data-ttu-id="877bc-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="877bc-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="877bc-114">**Encabezado:** CorHdr. h, Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="877bc-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="877bc-115">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="877bc-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="877bc-116">Consulte también</span><span class="sxs-lookup"><span data-stu-id="877bc-116">See also</span></span>

- [<span data-ttu-id="877bc-117">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="877bc-117">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="877bc-118">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="877bc-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="877bc-119">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="877bc-119">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
