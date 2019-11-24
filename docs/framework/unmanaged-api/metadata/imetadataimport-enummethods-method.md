---
title: IMetaDataImport::EnumMethods (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.EnumMethods
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::EnumMethods
helpviewer_keywords:
- IMetaDataImport::EnumMethods method [.NET Framework metadata]
- EnumMethods method [.NET Framework metadata]
ms.assetid: 8cc3b0c3-d97d-4f71-9e7d-ef2a92b4959a
topic_type:
- apiref
ms.openlocfilehash: 8e9e08ac903423b2e121f22cc9e43a660ccfac7b
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74450085"
---
# <a name="imetadataimportenummethods-method"></a><span data-ttu-id="6a957-102">IMetaDataImport::EnumMethods (Método)</span><span class="sxs-lookup"><span data-stu-id="6a957-102">IMetaDataImport::EnumMethods Method</span></span>
<span data-ttu-id="6a957-103">Enumera los tokens de MethodDef que representan métodos del tipo especificado.</span><span class="sxs-lookup"><span data-stu-id="6a957-103">Enumerates MethodDef tokens representing methods of the specified type.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6a957-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6a957-104">Syntax</span></span>  
  
```cpp  
HRESULT EnumMethods (  
   [in, out] HCORENUM   *phEnum,   
   [in]  mdTypeDef      cl,   
   [out] mdMethodDef    rMethods[],   
   [in]  ULONG          cMax,   
   [out] ULONG          *pcTokens  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6a957-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6a957-105">Parameters</span></span>  
 `phEnum`  
 <span data-ttu-id="6a957-106">[in, out] A pointer to the enumerator.</span><span class="sxs-lookup"><span data-stu-id="6a957-106">[in, out] A pointer to the enumerator.</span></span> <span data-ttu-id="6a957-107">This must be NULL for the first call of this method.</span><span class="sxs-lookup"><span data-stu-id="6a957-107">This must be NULL for the first call of this method.</span></span>  
  
 `cl`  
 <span data-ttu-id="6a957-108">[in] A TypeDef token representing the type with the methods to enumerate.</span><span class="sxs-lookup"><span data-stu-id="6a957-108">[in] A TypeDef token representing the type with the methods to enumerate.</span></span>  
  
 `rMethods`  
 <span data-ttu-id="6a957-109">[out] The array to store the MethodDef tokens.</span><span class="sxs-lookup"><span data-stu-id="6a957-109">[out] The array to store the MethodDef tokens.</span></span>  
  
 `cMax`  
 <span data-ttu-id="6a957-110">[in] The maximum size of the MethodDef `rMethods` array.</span><span class="sxs-lookup"><span data-stu-id="6a957-110">[in] The maximum size of the MethodDef `rMethods` array.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="6a957-111">[out] The number of MethodDef tokens returned in `rMethods`.</span><span class="sxs-lookup"><span data-stu-id="6a957-111">[out] The number of MethodDef tokens returned in `rMethods`.</span></span>  
  
## <a name="return-value"></a><span data-ttu-id="6a957-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="6a957-112">Return Value</span></span>  
  
|<span data-ttu-id="6a957-113">HRESULT</span><span class="sxs-lookup"><span data-stu-id="6a957-113">HRESULT</span></span>|<span data-ttu-id="6a957-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="6a957-114">Description</span></span>|  
|-------------|-----------------|  
|`S_OK`|<span data-ttu-id="6a957-115">`EnumMethods` returned successfully.</span><span class="sxs-lookup"><span data-stu-id="6a957-115">`EnumMethods` returned successfully.</span></span>|  
|`S_FALSE`|<span data-ttu-id="6a957-116">There are no MethodDef tokens to enumerate.</span><span class="sxs-lookup"><span data-stu-id="6a957-116">There are no MethodDef tokens to enumerate.</span></span> <span data-ttu-id="6a957-117">In that case, `pcTokens` is zero.</span><span class="sxs-lookup"><span data-stu-id="6a957-117">In that case, `pcTokens` is zero.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="6a957-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6a957-118">Requirements</span></span>  
 <span data-ttu-id="6a957-119">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6a957-119">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6a957-120">**Header:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="6a957-120">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6a957-121">**Library:** Included as a resource in MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="6a957-121">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6a957-122">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6a957-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6a957-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="6a957-123">See also</span></span>

- [<span data-ttu-id="6a957-124">IMetaDataImport (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a957-124">IMetaDataImport Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [<span data-ttu-id="6a957-125">IMetaDataImport2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6a957-125">IMetaDataImport2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
