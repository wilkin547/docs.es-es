---
title: IMetaDataImport::EnumTypeRefs (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeRefs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeRefs
helpviewer_keywords:
- EnumTypeRefs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeRefs method [.NET Framework metadata]
ms.assetid: b4896b8f-8e97-469c-8089-e72a025661b5
topic_type:
- apiref
ms.openlocfilehash: e5d4ddd43b27d733a63c2e0dc5e92ffd2ba94a7f
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175439"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="9f705-102">IMetaDataImport::EnumTypeRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="9f705-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="9f705-103">Enumera los tokens de TypeRef definidos en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="9f705-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9f705-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9f705-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9f705-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9f705-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="9f705-106">[adentro, fuera] Un puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="9f705-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="9f705-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="9f705-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="9f705-108">[fuera] Matriz utilizada para almacenar los tokens TypeRef.</span><span class="sxs-lookup"><span data-stu-id="9f705-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="9f705-109">[in] Tamaño máximo de la matriz `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="9f705-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="9f705-110">[fuera] Puntero al número de tokens TypeRef devueltos en `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="9f705-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="9f705-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9f705-111">Return Value</span></span>  
  
|<span data-ttu-id="9f705-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="9f705-112">HRESULT</span></span>|<span data-ttu-id="9f705-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="9f705-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="9f705-114">`EnumTypeRefs`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="9f705-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="9f705-115">No hay tokens para enumerar.</span><span class="sxs-lookup"><span data-stu-id="9f705-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="9f705-116">En ese `pcTypeRefs` caso, es cero.</span><span class="sxs-lookup"><span data-stu-id="9f705-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="9f705-117">Observaciones</span><span class="sxs-lookup"><span data-stu-id="9f705-117">Remarks</span></span>  
 <span data-ttu-id="9f705-118">Un token TypeRef representa una referencia a un tipo.</span><span class="sxs-lookup"><span data-stu-id="9f705-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9f705-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9f705-119">Requirements</span></span>  
 <span data-ttu-id="9f705-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9f705-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9f705-121">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="9f705-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="9f705-122">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="9f705-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="9f705-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9f705-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9f705-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="9f705-124">See also</span></span>

- [<span data-ttu-id="9f705-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9f705-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="9f705-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="9f705-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
