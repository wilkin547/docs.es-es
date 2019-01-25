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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 8d096be8eb7f966d5a79e57a3a1b7ab7f63cd5ea
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54659259"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="8b023-102">IMetaDataImport::EnumTypeRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="8b023-102">IMetaDataImport::EnumTypeRefs Method</span></span>
<span data-ttu-id="8b023-103">Enumera los tokens de TypeRef definidos en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="8b023-103">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b023-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8b023-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,   
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,   
   [out] ULONG           *pcTypeRefs  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="8b023-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8b023-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="8b023-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="8b023-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="8b023-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="8b023-107">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="8b023-108">[out] Matriz utilizada para almacenar los tokens de TypeRef.</span><span class="sxs-lookup"><span data-stu-id="8b023-108">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="8b023-109">[in] Tamaño máximo de la matriz `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="8b023-109">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="8b023-110">[out] Un puntero al número de tokens de TypeRef devuelto en `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="8b023-110">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="8b023-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8b023-111">Return Value</span></span>  
  
|<span data-ttu-id="8b023-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="8b023-112">HRESULT</span></span>|<span data-ttu-id="8b023-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="8b023-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="8b023-114">`EnumTypeRefs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="8b023-114">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="8b023-115">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="8b023-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="8b023-116">En ese caso, `pcTypeRefs` es cero.</span><span class="sxs-lookup"><span data-stu-id="8b023-116">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8b023-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8b023-117">Remarks</span></span>  
 <span data-ttu-id="8b023-118">Un símbolo (token) de TypeRef representa una referencia a un tipo.</span><span class="sxs-lookup"><span data-stu-id="8b023-118">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b023-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8b023-119">Requirements</span></span>  
 <span data-ttu-id="8b023-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8b023-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b023-121">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="8b023-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8b023-122">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8b023-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8b023-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8b023-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8b023-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="8b023-124">See also</span></span>
- [<span data-ttu-id="8b023-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8b023-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="8b023-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8b023-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
