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
ms.openlocfilehash: e77520552eea9b58e4358cc5928e5ce666037009
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95678160"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="3df54-102">IMetaDataImport::EnumTypeRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="3df54-102">IMetaDataImport::EnumTypeRefs Method</span></span>

<span data-ttu-id="3df54-103">Enumera los tokens de TypeRef definidos en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="3df54-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3df54-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3df54-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="3df54-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3df54-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="3df54-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="3df54-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="3df54-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="3df54-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="3df54-108">enuncia Matriz que se usa para almacenar los tokens de TypeRef.</span><span class="sxs-lookup"><span data-stu-id="3df54-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="3df54-109">[in] Tamaño máximo de la matriz `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="3df54-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="3df54-110">enuncia Puntero al número de tokens de TypeRef devueltos en `rTypeRefs` .</span><span class="sxs-lookup"><span data-stu-id="3df54-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="3df54-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3df54-111">Return Value</span></span>  
  
|<span data-ttu-id="3df54-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="3df54-112">HRESULT</span></span>|<span data-ttu-id="3df54-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="3df54-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="3df54-114">`EnumTypeRefs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="3df54-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="3df54-115">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="3df54-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="3df54-116">En ese caso, `pcTypeRefs` es cero.</span><span class="sxs-lookup"><span data-stu-id="3df54-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="3df54-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3df54-117">Remarks</span></span>  

 <span data-ttu-id="3df54-118">Un token TypeRef representa una referencia a un tipo.</span><span class="sxs-lookup"><span data-stu-id="3df54-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="3df54-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3df54-119">Requirements</span></span>  

 <span data-ttu-id="3df54-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3df54-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3df54-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="3df54-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="3df54-122">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="3df54-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="3df54-123">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="3df54-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3df54-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="3df54-124">See also</span></span>

- [<span data-ttu-id="3df54-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3df54-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="3df54-126">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="3df54-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
