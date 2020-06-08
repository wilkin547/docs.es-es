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
ms.openlocfilehash: 94b4c3935c949c0c4008e41244713b6bfa4dba84
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84503723"
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="f25bd-102">IMetaDataImport::EnumTypeSpecs (Método)</span><span class="sxs-lookup"><span data-stu-id="f25bd-102">IMetaDataImport::EnumTypeSpecs Method</span></span>
<span data-ttu-id="f25bd-103">Enumera los tokens de TypeSpec definidos en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="f25bd-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f25bd-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f25bd-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f25bd-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f25bd-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="f25bd-106">[in, out] Puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="f25bd-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="f25bd-107">Este valor debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="f25bd-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="f25bd-108">enuncia Matriz usada para almacenar los tokens de TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="f25bd-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="f25bd-109">[in] Tamaño máximo de la matriz `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="f25bd-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="f25bd-110">enuncia Número de tokens de TypeSpec devueltos en `rTypeSpecs` .</span><span class="sxs-lookup"><span data-stu-id="f25bd-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="f25bd-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f25bd-111">Return Value</span></span>  
  
|<span data-ttu-id="f25bd-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="f25bd-112">HRESULT</span></span>|<span data-ttu-id="f25bd-113">Description</span><span class="sxs-lookup"><span data-stu-id="f25bd-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="f25bd-114">`EnumTypeSpecs`se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="f25bd-114">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="f25bd-115">No hay tokens que enumerar.</span><span class="sxs-lookup"><span data-stu-id="f25bd-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="f25bd-116">En ese caso, `pcTypeSpecs` es cero.</span><span class="sxs-lookup"><span data-stu-id="f25bd-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="f25bd-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f25bd-117">Remarks</span></span>  
 <span data-ttu-id="f25bd-118">El método [IMetaDataEmit:: GetTokenFromTypeSpec (](imetadataemit-gettokenfromtypespec-method.md) crea los tokens TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="f25bd-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f25bd-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f25bd-119">Requirements</span></span>  
 <span data-ttu-id="f25bd-120">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f25bd-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f25bd-121">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="f25bd-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="f25bd-122">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="f25bd-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="f25bd-123">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f25bd-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f25bd-124">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="f25bd-124">See also</span></span>

- [<span data-ttu-id="f25bd-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f25bd-125">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="f25bd-126">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="f25bd-126">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
