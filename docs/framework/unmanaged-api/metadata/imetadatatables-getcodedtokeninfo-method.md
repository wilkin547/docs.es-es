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
ms.openlocfilehash: 8ab16ad5b2b2838125e07511ef47be737f40671c
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501214"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="07ba1-102">IMetaDataTables::GetCodedTokenInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="07ba1-102">IMetaDataTables::GetCodedTokenInfo Method</span></span>
<span data-ttu-id="07ba1-103">Obtiene un puntero a una matriz de tokens asociada al índice de fila especificado.</span><span class="sxs-lookup"><span data-stu-id="07ba1-103">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="07ba1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07ba1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetCodedTokenInfo (
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="07ba1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="07ba1-105">Parameters</span></span>  
 `ixCdTkn`  
 <span data-ttu-id="07ba1-106">de El tipo de token codificado que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="07ba1-106">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="07ba1-107">enuncia Puntero a la longitud de `ppTokens` .</span><span class="sxs-lookup"><span data-stu-id="07ba1-107">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="07ba1-108">enuncia Un puntero a un puntero a una matriz que contiene la lista de tokens devueltos.</span><span class="sxs-lookup"><span data-stu-id="07ba1-108">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="07ba1-109">enuncia Un puntero a un puntero al nombre del token en `ixCdTkn` .</span><span class="sxs-lookup"><span data-stu-id="07ba1-109">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="07ba1-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="07ba1-110">Requirements</span></span>  
 <span data-ttu-id="07ba1-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07ba1-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="07ba1-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="07ba1-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="07ba1-113">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="07ba1-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="07ba1-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07ba1-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="07ba1-115">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="07ba1-115">See also</span></span>

- [<span data-ttu-id="07ba1-116">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="07ba1-116">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="07ba1-117">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="07ba1-117">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
