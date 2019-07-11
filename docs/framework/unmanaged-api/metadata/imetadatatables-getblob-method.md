---
title: IMetaDataTables::GetBlob (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetBlob
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetBlob
helpviewer_keywords:
- GetBlob method [.NET Framework metadata]
- IMetaDataTables::GetBlob method [.NET Framework metadata]
ms.assetid: 94667c1c-6d58-4aa7-b74e-530b11e2a276
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 83f8ae068552ba83a016b5484e3ac6641417fa99
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781561"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="8cb5a-102">IMetaDataTables::GetBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="8cb5a-102">IMetaDataTables::GetBlob Method</span></span>
<span data-ttu-id="8cb5a-103">Obtiene un puntero para el objeto binario grande (BLOB) en el índice de la columna especificada.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8cb5a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8cb5a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8cb5a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8cb5a-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="8cb5a-106">[in] La dirección de memoria del que se obtienen `ppData`.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="8cb5a-107">[out] Un puntero al tamaño, en bytes, de `ppData`.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="8cb5a-108">[out] Recupera un puntero a un puntero a los datos binarios.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8cb5a-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8cb5a-109">Requirements</span></span>  
 <span data-ttu-id="8cb5a-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8cb5a-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8cb5a-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="8cb5a-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8cb5a-112">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="8cb5a-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8cb5a-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8cb5a-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8cb5a-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="8cb5a-114">See also</span></span>

- [<span data-ttu-id="8cb5a-115">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8cb5a-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="8cb5a-116">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="8cb5a-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
