---
description: 'Más información sobre: IMetaDataImport:: EnumUserStrings ((método)'
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
ms.openlocfilehash: a4ead696f3d924fef9ebfed5c4f1eb97eb13e14e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799322"
---
# <a name="imetadataimportenumuserstrings-method"></a><span data-ttu-id="4b0dd-103">IMetaDataImport::EnumUserStrings (Método)</span><span class="sxs-lookup"><span data-stu-id="4b0dd-103">IMetaDataImport::EnumUserStrings Method</span></span>

<span data-ttu-id="4b0dd-104">Enumera los tokens de String que representan las cadenas codificadas de forma rígida en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="4b0dd-104">Enumerates String tokens representing hard-coded strings in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4b0dd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4b0dd-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumUserStrings (  
   [in, out]  HCORENUM    *phEnum,  
   [out]  mdString        rStrings[],  
   [in]   ULONG           cMax,  
   [out]  ULONG           *pcStrings  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4b0dd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4b0dd-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="4b0dd-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="4b0dd-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="4b0dd-108">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="4b0dd-108">This must be NULL for the first call of this method.</span></span>  
  
 `rStrings`  
 <span data-ttu-id="4b0dd-109">enuncia Matriz que se usa para almacenar los tokens de cadena.</span><span class="sxs-lookup"><span data-stu-id="4b0dd-109">[out] The array used to store the String tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4b0dd-110">[in] Tamaño máximo de la matriz `rStrings`.</span><span class="sxs-lookup"><span data-stu-id="4b0dd-110">[in] The maximum size of the `rStrings` array.</span></span>  
  
 `pcStrings`  
 <span data-ttu-id="4b0dd-111">enuncia El número de tokens de cadena devueltos en `rStrings` .</span><span class="sxs-lookup"><span data-stu-id="4b0dd-111">[out] The number of String tokens returned in `rStrings`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4b0dd-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4b0dd-112">Return Value</span></span>  
  
|<span data-ttu-id="4b0dd-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4b0dd-113">HRESULT</span></span>|<span data-ttu-id="4b0dd-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="4b0dd-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4b0dd-115">`EnumUserStrings` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4b0dd-115">`EnumUserStrings` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4b0dd-116">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="4b0dd-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="4b0dd-117">En ese caso, `pcStrings` es cero.</span><span class="sxs-lookup"><span data-stu-id="4b0dd-117">In that case, `pcStrings` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4b0dd-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="4b0dd-118">Remarks</span></span>  

 <span data-ttu-id="4b0dd-119">Los tokens de cadena se crean mediante el método [IMetaDataEmit::D efineuserstring](imetadataemit-defineuserstring-method.md) .</span><span class="sxs-lookup"><span data-stu-id="4b0dd-119">The String tokens are created by the [IMetaDataEmit::DefineUserString](imetadataemit-defineuserstring-method.md) method.</span></span> <span data-ttu-id="4b0dd-120">Este método está diseñado para que lo use un explorador de metadatos en lugar de un compilador.</span><span class="sxs-lookup"><span data-stu-id="4b0dd-120">This method is designed to be used by a metadata browser rather than by a compiler.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4b0dd-121">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4b0dd-121">Requirements</span></span>  

 <span data-ttu-id="4b0dd-122">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4b0dd-122">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4b0dd-123">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="4b0dd-123">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4b0dd-124">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4b0dd-124">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4b0dd-125">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4b0dd-125">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4b0dd-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="4b0dd-126">See also</span></span>

- [<span data-ttu-id="4b0dd-127">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4b0dd-127">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="4b0dd-128">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="4b0dd-128">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
