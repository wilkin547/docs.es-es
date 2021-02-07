---
description: 'Más información acerca de: IMetaDataTables:: Getcodedtokeninfo ((método)'
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
ms.openlocfilehash: 982a13636d8b4572113038eaa658158e6c2ca966
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688291"
---
# <a name="imetadatatablesgetcodedtokeninfo-method"></a><span data-ttu-id="11a23-103">IMetaDataTables::GetCodedTokenInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="11a23-103">IMetaDataTables::GetCodedTokenInfo Method</span></span>

<span data-ttu-id="11a23-104">Obtiene un puntero a una matriz de tokens asociada al índice de fila especificado.</span><span class="sxs-lookup"><span data-stu-id="11a23-104">Gets a pointer to an array of tokens associated with the specified row index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="11a23-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="11a23-105">Syntax</span></span>  
  
```cpp  
HRESULT GetCodedTokenInfo (
    [in]  ULONG       ixCdTkn,  
    [out] ULONG       *pcTokens,  
    [out] ULONG       **ppTokens,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="11a23-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="11a23-106">Parameters</span></span>  

 `ixCdTkn`  
 <span data-ttu-id="11a23-107">de El tipo de token codificado que se va a devolver.</span><span class="sxs-lookup"><span data-stu-id="11a23-107">[in] The kind of coded token to return.</span></span>  
  
 `pcTokens`  
 <span data-ttu-id="11a23-108">enuncia Puntero a la longitud de `ppTokens` .</span><span class="sxs-lookup"><span data-stu-id="11a23-108">[out] A pointer to the length of `ppTokens`.</span></span>  
  
 `ppTokens`  
 <span data-ttu-id="11a23-109">enuncia Un puntero a un puntero a una matriz que contiene la lista de tokens devueltos.</span><span class="sxs-lookup"><span data-stu-id="11a23-109">[out] A pointer to a pointer to an array that contains the list of returned tokens.</span></span>  
  
 `ppName`  
 <span data-ttu-id="11a23-110">enuncia Un puntero a un puntero al nombre del token en `ixCdTkn` .</span><span class="sxs-lookup"><span data-stu-id="11a23-110">[out] A pointer to a pointer to the name of the token at `ixCdTkn`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="11a23-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="11a23-111">Requirements</span></span>  

 <span data-ttu-id="11a23-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="11a23-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="11a23-113">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="11a23-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="11a23-114">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="11a23-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="11a23-115">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="11a23-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="11a23-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="11a23-116">See also</span></span>

- [<span data-ttu-id="11a23-117">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a23-117">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="11a23-118">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="11a23-118">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
