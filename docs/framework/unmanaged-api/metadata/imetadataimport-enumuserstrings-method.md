---
title: IMetaDataImport::EnumUserStrings (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumUserStrings
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumUserStrings
helpviewer_keywords:
- IMetaDataImport::EnumUserStrings method [.NET Framework metadata]
- EnumUserStrings method [.NET Framework metadata]
ms.assetid: 2b1f1418-4be8-4cdb-b418-b3abccc527a7
topic_type:
- apiref
ms.openlocfilehash: 1c9f15881d3515f24a63f29e9337a7a356937f2d
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449943"
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="2312a-102">IMetaDataImport::EnumUserStrings (Método)</span><span class="sxs-lookup"><span data-stu-id="2312a-102">IMetaDataImport::EnumUserStrings Method</span></span>
<span data-ttu-id="2312a-103">Enumera los tokens de String que representan las cadenas codificadas de forma rígida en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="2312a-103">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2312a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2312a-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2312a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2312a-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="2312a-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="2312a-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="2312a-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="2312a-107">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="2312a-108">enuncia Matriz que se usa para almacenar los tokens de cadena.</span><span class="sxs-lookup"><span data-stu-id="2312a-108">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2312a-109">[in] Tamaño máximo de la matriz `rStrings`.</span><span class="sxs-lookup"><span data-stu-id="2312a-109">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="2312a-110">enuncia El número de tokens de cadena devueltos en `rStrings`.</span><span class="sxs-lookup"><span data-stu-id="2312a-110">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2312a-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2312a-111">Return Value</span></span>  
  
|<span data-ttu-id="2312a-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2312a-112">HRESULT</span></span>|<span data-ttu-id="2312a-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="2312a-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2312a-114">`EnumUserStrings` devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2312a-114">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2312a-115">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="2312a-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="2312a-116">En ese caso, `pcStrings` es cero.</span><span class="sxs-lookup"><span data-stu-id="2312a-116">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2312a-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2312a-117">Remarks</span></span>  
 <span data-ttu-id="2312a-118">Los tokens de cadena se crean mediante el método [IMetaDataEmit::D efineuserstring](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) .</span><span class="sxs-lookup"><span data-stu-id="2312a-118">The String tokens are created by the [IMetaDataEmit::DefineUserString](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="2312a-119">Este método está diseñado para que lo use un explorador de metadatos en lugar de un compilador.</span><span class="sxs-lookup"><span data-stu-id="2312a-119">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2312a-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2312a-120">Requirements</span></span>  
 <span data-ttu-id="2312a-121">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2312a-121">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2312a-122">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2312a-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2312a-123">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="2312a-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2312a-124">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2312a-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2312a-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="2312a-125">See also</span></span>

- [<span data-ttu-id="2312a-126">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2312a-126">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="2312a-127">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2312a-127">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
