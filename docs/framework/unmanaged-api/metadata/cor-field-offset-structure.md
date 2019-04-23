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
ms.openlocfilehash: 820c99de1bdb108a24203a3438b1709ca54490b7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59078127"
---
# <a name="corfieldoffset-structure"></a><span data-ttu-id="34feb-102">COR_FIELD_OFFSET (Estructura)</span><span class="sxs-lookup"><span data-stu-id="34feb-102">COR_FIELD_OFFSET Structure</span></span>
<span data-ttu-id="34feb-103">Almacena el desplazamiento, dentro de una clase, del campo especificado.</span><span class="sxs-lookup"><span data-stu-id="34feb-103">Stores the offset, within a class, of the specified field.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="34feb-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="34feb-104">Syntax</span></span>  
  
```  
typedef struct COR_FIELD_OFFSET {  
    mdFieldDef  ridOfField;  
    ULONG       ulOffset;  
} COR_FIELD_OFFSET;  
```  
  
## <a name="members"></a><span data-ttu-id="34feb-105">Miembros</span><span class="sxs-lookup"><span data-stu-id="34feb-105">Members</span></span>  
  
|<span data-ttu-id="34feb-106">Miembro</span><span class="sxs-lookup"><span data-stu-id="34feb-106">Member</span></span>|<span data-ttu-id="34feb-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="34feb-107">Description</span></span>|  
|------------|-----------------|  
|`ridOfField`|<span data-ttu-id="34feb-108">Un `mdFieldDef` token de metadatos que representa el campo.</span><span class="sxs-lookup"><span data-stu-id="34feb-108">An `mdFieldDef` metadata token that represents the field.</span></span>|  
|`ulOffset`|<span data-ttu-id="34feb-109">El desplazamiento del campo dentro de su clase.</span><span class="sxs-lookup"><span data-stu-id="34feb-109">The field's offset within its class.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="34feb-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="34feb-110">Remarks</span></span>  
 <span data-ttu-id="34feb-111">[GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) y [SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) métodos toman un parámetro de tipo `COR_FIELD_OFFSET`.</span><span class="sxs-lookup"><span data-stu-id="34feb-111">[IMetaDataImport::GetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-getclasslayout-method.md) and [IMetaDataEmit::SetClassLayout](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-setclasslayout-method.md) methods take a parameter of type `COR_FIELD_OFFSET`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="34feb-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="34feb-112">Requirements</span></span>  
 <span data-ttu-id="34feb-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="34feb-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="34feb-114">**Encabezado**: CorHdr.h, CorProf.idl</span><span class="sxs-lookup"><span data-stu-id="34feb-114">**Header:** CorHdr.h, CorProf.idl</span></span>  
  
 <span data-ttu-id="34feb-115">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="34feb-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="34feb-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="34feb-116">See also</span></span>

- [<span data-ttu-id="34feb-117">Estructuras de metadatos</span><span class="sxs-lookup"><span data-stu-id="34feb-117">Metadata Structures</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-structures.md)
- [<span data-ttu-id="34feb-118">IMetaDataEmit (interfaz)</span><span class="sxs-lookup"><span data-stu-id="34feb-118">IMetaDataEmit Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [<span data-ttu-id="34feb-119">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="34feb-119">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
