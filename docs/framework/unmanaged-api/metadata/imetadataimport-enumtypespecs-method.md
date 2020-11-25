---
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
ms.openlocfilehash: 38c9f8df12b0fc83a236d2cb7c32d1198be7096d
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719819"
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="2beb9-102">IMetaDataImport::EnumTypeSpecs (Método)</span><span class="sxs-lookup"><span data-stu-id="2beb9-102">IMetaDataImport::EnumTypeSpecs Method</span></span>

<span data-ttu-id="2beb9-103">Enumera los tokens de TypeSpec definidos en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="2beb9-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2beb9-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2beb9-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2beb9-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2beb9-105">Parameters</span></span>  

 `phEnum`  
 <span data-ttu-id="2beb9-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="2beb9-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="2beb9-107">Este valor debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="2beb9-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="2beb9-108">enuncia Matriz usada para almacenar los tokens de TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="2beb9-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="2beb9-109">[in] Tamaño máximo de la matriz `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="2beb9-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="2beb9-110">enuncia Número de tokens de TypeSpec devueltos en `rTypeSpecs` .</span><span class="sxs-lookup"><span data-stu-id="2beb9-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="2beb9-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2beb9-111">Return Value</span></span>  
  
|<span data-ttu-id="2beb9-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="2beb9-112">HRESULT</span></span>|<span data-ttu-id="2beb9-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="2beb9-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="2beb9-114">`EnumTypeSpecs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="2beb9-114">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="2beb9-115">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="2beb9-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="2beb9-116">En ese caso, `pcTypeSpecs` es cero.</span><span class="sxs-lookup"><span data-stu-id="2beb9-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="2beb9-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2beb9-117">Remarks</span></span>  

 <span data-ttu-id="2beb9-118">El método [IMetaDataEmit:: GetTokenFromTypeSpec (](imetadataemit-gettokenfromtypespec-method.md) crea los tokens TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="2beb9-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2beb9-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2beb9-119">Requirements</span></span>  

 <span data-ttu-id="2beb9-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2beb9-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2beb9-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="2beb9-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2beb9-122">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2beb9-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2beb9-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2beb9-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2beb9-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="2beb9-124">See also</span></span>

- [<span data-ttu-id="2beb9-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2beb9-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="2beb9-126">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="2beb9-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
