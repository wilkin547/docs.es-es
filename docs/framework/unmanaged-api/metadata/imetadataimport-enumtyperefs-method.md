---
description: 'Más información sobre: IMetaDataImport:: Enumtyperefs ((método)'
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
ms.openlocfilehash: 1155357e82c08660a852225f0b1a54629cbee0ca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670637"
---
# <a name="imetadataimportenumtyperefs-method"></a><span data-ttu-id="5ca87-103">IMetaDataImport::EnumTypeRefs (Método)</span><span class="sxs-lookup"><span data-stu-id="5ca87-103">IMetaDataImport::EnumTypeRefs Method</span></span>

<span data-ttu-id="5ca87-104">Enumera los tokens de TypeRef definidos en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="5ca87-104">Enumerates TypeRef tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ca87-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5ca87-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeRefs (  
   [in, out] HCORENUM    *phEnum,
   [out] mdTypeRef       rTypeRefs[],  
   [in]  ULONG           cMax,
   [out] ULONG           *pcTypeRefs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ca87-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5ca87-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="5ca87-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="5ca87-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="5ca87-108">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="5ca87-108">This must be NULL for the first call of this method.</span></span>  
  
 `rTypeRefs`  
 <span data-ttu-id="5ca87-109">enuncia Matriz que se usa para almacenar los tokens de TypeRef.</span><span class="sxs-lookup"><span data-stu-id="5ca87-109">[out] The array used to store the TypeRef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="5ca87-110">[in] Tamaño máximo de la matriz `rTypeRefs`.</span><span class="sxs-lookup"><span data-stu-id="5ca87-110">[in] The maximum size of the `rTypeRefs` array.</span></span>  
  
 `pcTypeRefs`  
 <span data-ttu-id="5ca87-111">enuncia Puntero al número de tokens de TypeRef devueltos en `rTypeRefs` .</span><span class="sxs-lookup"><span data-stu-id="5ca87-111">[out] A pointer to the number of TypeRef tokens returned in `rTypeRefs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="5ca87-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5ca87-112">Return Value</span></span>  
  
|<span data-ttu-id="5ca87-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="5ca87-113">HRESULT</span></span>|<span data-ttu-id="5ca87-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="5ca87-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="5ca87-115">`EnumTypeRefs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="5ca87-115">`EnumTypeRefs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="5ca87-116">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="5ca87-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="5ca87-117">En ese caso, `pcTypeRefs` es cero.</span><span class="sxs-lookup"><span data-stu-id="5ca87-117">In that case, `pcTypeRefs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="5ca87-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="5ca87-118">Remarks</span></span>  

 <span data-ttu-id="5ca87-119">Un token TypeRef representa una referencia a un tipo.</span><span class="sxs-lookup"><span data-stu-id="5ca87-119">A TypeRef token represents a reference to a type.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5ca87-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5ca87-120">Requirements</span></span>  

 <span data-ttu-id="5ca87-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5ca87-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5ca87-122">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="5ca87-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="5ca87-123">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="5ca87-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="5ca87-124">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5ca87-124">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5ca87-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="5ca87-125">See also</span></span>

- [<span data-ttu-id="5ca87-126">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ca87-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="5ca87-127">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="5ca87-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
