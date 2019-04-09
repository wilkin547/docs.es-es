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
ms.openlocfilehash: 01151dc2fe6aa995285a34076527609816b2f3e8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59205165"
---
# <a name="imetadataimportenumtypespecs-method"></a><span data-ttu-id="77518-102">IMetaDataImport::EnumTypeSpecs (Método)</span><span class="sxs-lookup"><span data-stu-id="77518-102">IMetaDataImport::EnumTypeSpecs Method</span></span>
<span data-ttu-id="77518-103">Enumera los tokens de TypeSpec definidos en el ámbito de metadatos actual.</span><span class="sxs-lookup"><span data-stu-id="77518-103">Enumerates TypeSpec tokens defined in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="77518-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="77518-104">Syntax</span></span>  
  
```  
HRESULT EnumTypeSpecs (  
   [in, out] HCORENUM    *phEnum,  
   [out] mdTypeSpec      rTypeSpecs[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTypeSpecs  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="77518-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="77518-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="77518-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="77518-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="77518-107">Este valor debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="77518-107">This value must be NULL for the first call of this method.</span></span>  
  
 `rTypeSpecs`  
 <span data-ttu-id="77518-108">[out] Matriz utilizada para almacenar los tokens de TypeSpec.</span><span class="sxs-lookup"><span data-stu-id="77518-108">[out] The array used to store the TypeSpec tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="77518-109">[in] Tamaño máximo de la matriz `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="77518-109">[in] The maximum size of the `rTypeSpecs` array.</span></span>  
  
 `pcTypeSpecs`  
 <span data-ttu-id="77518-110">[out] El número de tokens de TypeSpec devueltos en `rTypeSpecs`.</span><span class="sxs-lookup"><span data-stu-id="77518-110">[out] The number of TypeSpec tokens returned in `rTypeSpecs`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="77518-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="77518-111">Return Value</span></span>  
  
|<span data-ttu-id="77518-112">HRESULT</span><span class="sxs-lookup"><span data-stu-id="77518-112">HRESULT</span></span>|<span data-ttu-id="77518-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="77518-113">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|`EnumTypeSpecs` <span data-ttu-id="77518-114">se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="77518-114">returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="77518-115">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="77518-115">There are no tokens to enumerate.</span></span> <span data-ttu-id="77518-116">En ese caso, `pcTypeSpecs` es cero.</span><span class="sxs-lookup"><span data-stu-id="77518-116">In that case, `pcTypeSpecs` is zero.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="77518-117">Comentarios</span><span class="sxs-lookup"><span data-stu-id="77518-117">Remarks</span></span>  
 <span data-ttu-id="77518-118">Los tokens de TypeSpec se crean mediante el [GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) método.</span><span class="sxs-lookup"><span data-stu-id="77518-118">The TypeSpec tokens are created by the [IMetaDataEmit::GetTokenFromTypeSpec](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-gettokenfromtypespec-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="77518-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="77518-119">Requirements</span></span>  
 <span data-ttu-id="77518-120">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="77518-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="77518-121">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="77518-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="77518-122">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="77518-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="77518-123">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="77518-123">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="77518-124">Vea también</span><span class="sxs-lookup"><span data-stu-id="77518-124">See also</span></span>

- [<span data-ttu-id="77518-125">IMetaDataImport (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="77518-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="77518-126">IMetaDataImport2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="77518-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
