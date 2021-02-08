---
description: 'Más información sobre: IMetaDataImport:: Enumtypespecs ((método)'
title: IMetaDataImport::EnumTypeSpecs (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumTypeSpecs
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumTypeSpecs
helpviewer_keywords:
- EnumTypeSpecs method [.NET Framework metadata]
- IMetaDataImport::EnumTypeSpecs method [.NET Framework metadata]
ms.assetid: 75331c7b-988b-436c-9eb9-a270d37b4f06
topic_type:
- apiref
ms.openlocfilehash: 7446bbf3296ffb6cfa3a20f594b4a7da22acff5c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799348"
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="35698-103">IMetaDataImport::EnumTypeSpecs (Método)</span><span class="sxs-lookup"><span data-stu-id="35698-103">IMetaDataImport::EnumTypeSpecs Method</span></span>

<span data-ttu-id="35698-104">Enumera los tokens de TypeSpec definidos en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="35698-104">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="35698-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="35698-105">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="35698-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="35698-106">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="35698-107">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="35698-107">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="35698-108">Este valor debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="35698-108">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="35698-109">enuncia Matriz usada para almacenar los tokens de TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="35698-109">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="35698-110">[in] Tamaño máximo de la matriz `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="35698-110">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="35698-111">enuncia Número de tokens de TypeSpec devueltos en `rTypeSpecs` .</span><span class="sxs-lookup"><span data-stu-id="35698-111">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="35698-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="35698-112">Return Value</span></span>  
  
|<span data-ttu-id="35698-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="35698-113">HRESULT</span></span>|<span data-ttu-id="35698-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="35698-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="35698-115">`EnumTypeSpecs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="35698-115">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="35698-116">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="35698-116">There are no tokens to enumerate.</span></span> <span data-ttu-id="35698-117">En ese caso, `pcTypeSpecs` es cero.</span><span class="sxs-lookup"><span data-stu-id="35698-117">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="35698-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="35698-118">Remarks</span></span>  

 <span data-ttu-id="35698-119">El método [IMetaDataEmit:: GetTokenFromTypeSpec (](imetadataemit-gettokenfromtypespec-method.md) crea los tokens TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="35698-119">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="35698-120">Requisitos</span><span class="sxs-lookup"><span data-stu-id="35698-120">Requirements</span></span>  

 <span data-ttu-id="35698-121">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="35698-121">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="35698-122">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="35698-122">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="35698-123">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="35698-123">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="35698-124">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="35698-124">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="35698-125">Vea también</span><span class="sxs-lookup"><span data-stu-id="35698-125">See also</span></span>

- [<span data-ttu-id="35698-126">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="35698-126">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="35698-127">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="35698-127">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
