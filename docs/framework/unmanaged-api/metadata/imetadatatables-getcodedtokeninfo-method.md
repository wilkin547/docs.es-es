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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b89409a08ed2dff0111b3b6e552960ac78a5882e
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781532"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="03124-102">IMetaDataTables::GetCodedTokenInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="03124-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="03124-103">Obtiene un puntero a una matriz de tokens asociados con el índice de fila especificado.</span><span class="sxs-lookup"><span data-stu-id="03124-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="03124-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="03124-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodedTokenInfo (   
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="03124-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="03124-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="03124-106">[in] El tipo de token codificada que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="03124-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="03124-107">[out] Un puntero a la longitud de `ppTokens`.</span><span class="sxs-lookup"><span data-stu-id="03124-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="03124-108">[out] Un puntero a un puntero a una matriz que contiene la lista de tokens devueltos.</span><span class="sxs-lookup"><span data-stu-id="03124-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="03124-109">[out] Un puntero a un puntero al nombre del token en `ixCdTkn`.</span><span class="sxs-lookup"><span data-stu-id="03124-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="03124-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="03124-110">Requirements</span></span>  
 <span data-ttu-id="03124-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="03124-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="03124-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="03124-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="03124-113">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="03124-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="03124-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="03124-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="03124-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="03124-115">See also</span></span>

- [<span data-ttu-id="03124-116">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="03124-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="03124-117">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="03124-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
