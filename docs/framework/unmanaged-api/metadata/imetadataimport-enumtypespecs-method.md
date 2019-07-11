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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 81592b6da7fa7cdf275e9fa5b4b82ef0a15061c0
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67782566"
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="4e32c-102">IMetaDataImport::EnumTypeSpecs (Método)</span><span class="sxs-lookup"><span data-stu-id="4e32c-102">IMetaDataImport::EnumTypeSpecs Method</span></span>
<span data-ttu-id="4e32c-103">Enumera los tokens de TypeSpec definidos en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="4e32c-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4e32c-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e32c-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="4e32c-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4e32c-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="4e32c-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="4e32c-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="4e32c-107">Este valor debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="4e32c-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="4e32c-108">[out] Matriz utilizada para almacenar los tokens de TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="4e32c-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="4e32c-109">[in] Tamaño máximo de la matriz `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="4e32c-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="4e32c-110">[out] El número de tokens de TypeSpec devueltos en `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="4e32c-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="4e32c-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4e32c-111">Return Value</span></span>  
  
|<span data-ttu-id="4e32c-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="4e32c-112">HRESULT</span></span>|<span data-ttu-id="4e32c-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="4e32c-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="4e32c-114">`EnumTypeSpecs` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="4e32c-114">`EnumTypeSpecs` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="4e32c-115">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="4e32c-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="4e32c-116">En ese caso, `pcTypeSpecs` es cero.</span><span class="sxs-lookup"><span data-stu-id="4e32c-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="4e32c-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4e32c-117">Remarks</span></span>  
 <span data-ttu-id="4e32c-118">Los tokens de TypeSpec se crean mediante el [GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="4e32c-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4e32c-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e32c-119">Requirements</span></span>  
 <span data-ttu-id="4e32c-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e32c-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4e32c-121">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="4e32c-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="4e32c-122">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4e32c-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="4e32c-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e32c-123">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4e32c-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e32c-124">See also</span></span>

- [<span data-ttu-id="4e32c-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e32c-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="4e32c-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e32c-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
