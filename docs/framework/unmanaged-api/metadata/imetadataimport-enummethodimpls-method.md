---
title: IMetaDataImport::EnumMethodImpls (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethodImpls
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethodImpls
helpviewer_keywords:
- EnumMethodImpls method [.NET Framework metadata]
- IMetaDataImport::EnumMethodImpls method [.NET Framework metadata]
ms.assetid: 4e0f865d-88b5-44bd-be35-492622e5e08e
topic_type:
- apiref
ms.openlocfilehash: e766cec8fd84713e12c43cd1095650ed5b757bcb
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175478"
---
# <a name="imetadataimportenummethodimpls-method"></a><span data-ttu-id="7a275-102">IMetaDataImport::EnumMethodImpls (Método)</span><span class="sxs-lookup"><span data-stu-id="7a275-102">IMetaDataImport::EnumMethodImpls Method</span></span>
<span data-ttu-id="7a275-103">Enumera los tokens MethodBody y MethodDeclaration que representan métodos del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="7a275-103">Enumerates MethodBody and MethodDeclaration tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7a275-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7a275-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethodImpls (  
   [in, out] HCORENUM    *phEnum,
   [in]      mdTypeDef   td,
   [out]     mdToken     rMethodBody[],
   [out]     mdToken     rMethodDecl[],
   [in]      ULONG       cMax,
   [in]      ULONG       *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="7a275-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7a275-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="7a275-106">[adentro, fuera] Un puntero al enumerador.</span><span class="sxs-lookup"><span data-stu-id="7a275-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="7a275-107">Debe ser NULL para la primera llamada de este método.</span><span class="sxs-lookup"><span data-stu-id="7a275-107">This must be NULL for the first call of this method.</span></span>  
  
 `td`  
 <span data-ttu-id="7a275-108">[en] Un token TypeDef para el tipo cuyas implementaciones de método se van a enumerar.</span><span class="sxs-lookup"><span data-stu-id="7a275-108">[in] A TypeDef token for the type whose method implementations to enumerate.</span></span>  
  
 `rMethodBody`  
 <span data-ttu-id="7a275-109">[fuera] Matriz para almacenar los tokens MethodBody.</span><span class="sxs-lookup"><span data-stu-id="7a275-109">[out] The array to store the MethodBody tokens.</span></span>  
  
 `rMethodDecl`  
 <span data-ttu-id="7a275-110">[fuera] Matriz para almacenar los tokens MethodDeclaration.</span><span class="sxs-lookup"><span data-stu-id="7a275-110">[out] The array to store the MethodDeclaration tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="7a275-111">[en] El tamaño máximo `rMethodBody` `rMethodDecl` de las matrices y.</span><span class="sxs-lookup"><span data-stu-id="7a275-111">[in] The maximum size of the `rMethodBody` and `rMethodDecl` arrays.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="7a275-112">[en] El número real de `rMethodBody` `rMethodDecl`métodos devueltos en y .</span><span class="sxs-lookup"><span data-stu-id="7a275-112">[in] The actual number of methods returned in `rMethodBody` and `rMethodDecl`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="7a275-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7a275-113">Return Value</span></span>  
  
|<span data-ttu-id="7a275-114">HRESULT</span><span class="sxs-lookup"><span data-stu-id="7a275-114">HRESULT</span></span>|<span data-ttu-id="7a275-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="7a275-115">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="7a275-116">`EnumMethodImpls`regresó con éxito.</span><span class="sxs-lookup"><span data-stu-id="7a275-116">`EnumMethodImpls` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="7a275-117">No hay tokens de método para enumerar.</span><span class="sxs-lookup"><span data-stu-id="7a275-117">There are no method tokens to enumerate.</span></span> <span data-ttu-id="7a275-118">En ese `pcTokens` caso, es cero.</span><span class="sxs-lookup"><span data-stu-id="7a275-118">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7a275-119">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7a275-119">Requirements</span></span>  
 <span data-ttu-id="7a275-120">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7a275-120">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7a275-121">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="7a275-121">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="7a275-122">**Biblioteca:** Incluido como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7a275-122">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="7a275-123">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7a275-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7a275-124">Consulte también</span><span class="sxs-lookup"><span data-stu-id="7a275-124">See also</span></span>

- [<span data-ttu-id="7a275-125">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7a275-125">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="7a275-126">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="7a275-126">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
