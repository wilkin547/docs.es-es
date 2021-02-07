---
description: 'Más información acerca de: estructura de COR_FIELD_OFFSET'
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
ms.openlocfilehash: 7976e79a5484fa467d7ac887a4e1a7fa324abf69
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99678645"
---
# <a name="cor_field_offset-structure"></a><span data-ttu-id="859a2-103">COR_FIELD_OFFSET (Estructura)</span><span class="sxs-lookup"><span data-stu-id="859a2-103">COR_FIELD_OFFSET Structure</span></span>

<span data-ttu-id="859a2-104">Almacena el desplazamiento, dentro de una clase, del campo especificado.</span><span class="sxs-lookup"><span data-stu-id="859a2-104">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="859a2-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="859a2-105">Syntax</span></span>  
  
```cpp  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="859a2-106">Members</span><span class="sxs-lookup"><span data-stu-id="859a2-106">Members</span></span>  
  
|<span data-ttu-id="859a2-107">Miembro</span><span class="sxs-lookup"><span data-stu-id="859a2-107">Member</span></span>|<span data-ttu-id="859a2-108">Descripción</span><span class="sxs-lookup"><span data-stu-id="859a2-108">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="859a2-109">`mdFieldDef`Token de metadatos que representa el campo.</span><span class="sxs-lookup"><span data-stu-id="859a2-109">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="859a2-110">Desplazamiento del campo dentro de su clase.</span><span class="sxs-lookup"><span data-stu-id="859a2-110">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="859a2-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="859a2-111">Remarks</span></span>  

 <span data-ttu-id="859a2-112">Los métodos [IMetaDataImport:: GetClassLayout](imetadataimport-getclasslayout-method.md) y [IMetaDataEmit:: setclasslayout (](imetadataemit-setclasslayout-method.md) toman un parámetro de tipo `COR_FIELD_OFFSET` .</span><span class="sxs-lookup"><span data-stu-id="859a2-112">[IMetaDataImport::GetClassLayout](imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="859a2-113">Requisitos</span><span class="sxs-lookup"><span data-stu-id="859a2-113">Requirements</span></span>  

 <span data-ttu-id="859a2-114">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="859a2-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="859a2-115">**Encabezado:** CorHdr. h, Corprof. idl</span><span class="sxs-lookup"><span data-stu-id="859a2-115">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="859a2-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="859a2-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="859a2-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="859a2-117">See also</span></span>

- [<span data-ttu-id="859a2-118">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="859a2-118">Metadata Structures</span></span>](metadata-structures.md)
- [<span data-ttu-id="859a2-119">IMetaDataEmit (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="859a2-119">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="859a2-120">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="859a2-120">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
