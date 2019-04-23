---
title: IMetaDataImport::EnumMethodsWithName (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodsWithName
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodsWithName
helpviewer_keywords:
- IMetaDataImport::EnumMethodsWithName method [.NET Framework metadata]
- EnumMethodsWithName method [.NET Framework metadata]
ms.assetid: a8624913-2e23-46ad-a0c1-bb8eccbbf20f
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: f15ee906fb20cb60272cee3deffa68dbe852f689
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59200186"
---
# <a name="imetadataimportenummethodswithname-method"></a><span data-ttu-id="c43a8-102">IMetaDataImport::EnumMethodsWithName (Método)</span><span class="sxs-lookup"><span data-stu-id="c43a8-102">IMetaDataImport::EnumMethodsWithName Method</span></span>
<span data-ttu-id="c43a8-103">Enumera los métodos que tienen el nombre especificado y que están definidos por el tipo al que hace referencia el token de TypeDef especificado.</span><span class="sxs-lookup"><span data-stu-id="c43a8-103">Enumerates methods that have the specified name and that are defined by the type referenced by the specified TypeDef token.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c43a8-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c43a8-104">Syntax</span></span>  
  
```  
HRESULT EnumMethodsWithName (  
   [in, out] HCORENUM    *phEnum,  
   [in]  mdTypeDef       cl,  
   [in]  LPCWSTR         szName,  
   [out] mdMethodDef     rMethods[],  
   [in]  ULONG           cMax,  
   [out] ULONG           *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="c43a8-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c43a8-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="c43a8-106">[in, out] Un puntero en el enumerador.</span><span class="sxs-lookup"><span data-stu-id="c43a8-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="c43a8-107">Esto debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="c43a8-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="c43a8-108">[in] Un token de TypeDef que representa el tipo cuyos métodos para enumerar.</span><span class="sxs-lookup"><span data-stu-id="c43a8-108">[in] A TypeDef token representing the type whose methods to enumerate.</span></span>  
  
 `szName`  
 <span data-ttu-id="c43a8-109">[in] El nombre que limita el ámbito de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="c43a8-109">[in] The name that limits the scope of the enumeration.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="c43a8-110">[out] Matriz utilizada para almacenar los tokens de MethodDef.</span><span class="sxs-lookup"><span data-stu-id="c43a8-110">[out] The array used to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="c43a8-111">[in] Tamaño máximo de la matriz `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="c43a8-111">[in] The maximum size of the `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="c43a8-112">[out] El número de tokens de MethodDef devueltos en `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="c43a8-112">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c43a8-113">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c43a8-113">Remarks</span></span>  
 <span data-ttu-id="c43a8-114">Este método enumera los campos y métodos, pero no las propiedades o eventos.</span><span class="sxs-lookup"><span data-stu-id="c43a8-114">This method enumerates fields and methods, but not properties or events.</span></span> <span data-ttu-id="c43a8-115">A diferencia de [EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` descarta todos los tokens de método que no tienen el nombre especificado.</span><span class="sxs-lookup"><span data-stu-id="c43a8-115">Unlike [IMetaDataImport::EnumMethods](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-enummethods-method.md), `EnumMethodsWithName` discards all method tokens that do not have the specified name.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="c43a8-116">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c43a8-116">Return Value</span></span>  
  
|<span data-ttu-id="c43a8-117">HRESULT</span><span class="sxs-lookup"><span data-stu-id="c43a8-117">HRESULT</span></span>|<span data-ttu-id="c43a8-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="c43a8-118">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="c43a8-119">`EnumMethodsWithName` se devolvió correctamente.</span><span class="sxs-lookup"><span data-stu-id="c43a8-119">`EnumMethodsWithName` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="c43a8-120">No hay ningún token para enumerar.</span><span class="sxs-lookup"><span data-stu-id="c43a8-120">There are no tokens to enumerate.</span></span> <span data-ttu-id="c43a8-121">En ese caso, `pcTokens` es cero.</span><span class="sxs-lookup"><span data-stu-id="c43a8-121">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c43a8-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c43a8-122">Requirements</span></span>  
 <span data-ttu-id="c43a8-123">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c43a8-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c43a8-124">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="c43a8-124">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c43a8-125">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c43a8-125">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c43a8-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c43a8-126">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c43a8-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="c43a8-127">See also</span></span>

- [<span data-ttu-id="c43a8-128">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c43a8-128">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="c43a8-129">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c43a8-129">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
