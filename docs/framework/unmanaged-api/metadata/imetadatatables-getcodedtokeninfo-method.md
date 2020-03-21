---
title: IMetaDataTables::GetCodedTokenInfo (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetCodedTokenInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetCodedTokenInfo
helpviewer_keywords:
- GetCodedTokenInfo method [.NET Framework metadata]
- IMetaDataTables::GetCodedTokenInfo method [.NET Framework metadata]
ms.assetid: 31214d3a-715e-49af-92b3-0fd11e4f218a
topic_type:
- apiref
ms.openlocfilehash: 64c70fe0b657047ae35dccb763fa57120403deef
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177153"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="d557f-102">IMetaDataTables::GetCodedTokenInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="d557f-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="d557f-103">Obtiene un puntero a una matriz de tokens asociados con el índice de fila especificado.</span><span class="sxs-lookup"><span data-stu-id="d557f-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d557f-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d557f-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodedTokenInfo (
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d557f-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d557f-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="d557f-106">[en] El tipo de token codificado que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="d557f-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="d557f-107">[fuera] Un puntero a `ppTokens`la longitud de .</span><span class="sxs-lookup"><span data-stu-id="d557f-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="d557f-108">[fuera] Puntero a un puntero a una matriz que contiene la lista de tokens devueltos.</span><span class="sxs-lookup"><span data-stu-id="d557f-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="d557f-109">[fuera] Un puntero a un puntero al `ixCdTkn`nombre del token en .</span><span class="sxs-lookup"><span data-stu-id="d557f-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d557f-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d557f-110">Requirements</span></span>  
 <span data-ttu-id="d557f-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d557f-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d557f-112">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d557f-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d557f-113">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="d557f-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d557f-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d557f-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d557f-115">Consulte también</span><span class="sxs-lookup"><span data-stu-id="d557f-115">See also</span></span>

- [<span data-ttu-id="d557f-116">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d557f-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="d557f-117">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="d557f-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
