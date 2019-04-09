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
ms.openlocfilehash: babe098b16729cfcd41b48075a49b9ae9be7dfdc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59117188"
---
# <a name="imetadatatablesgetblob-method"></a><span data-ttu-id="0a9f1-102">IMetaDataTables::GetBlob (Método)</span><span class="sxs-lookup"><span data-stu-id="0a9f1-102">IMetaDataTables::GetBlob Method</span></span>
<span data-ttu-id="0a9f1-103">Obtiene un puntero para el objeto binario grande (BLOB) en el índice de la columna especificada.</span><span class="sxs-lookup"><span data-stu-id="0a9f1-103">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0a9f1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0a9f1-104">Syntax</span></span>  
  
```  
HRESULT GetBlob (  
    [in]  ULONG          ixBlob,  
    [out] ULONG          *pcbData,  
    [out] const void     **ppData  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="0a9f1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0a9f1-105">Parameters</span></span>  
 `ixBlob`  
 <span data-ttu-id="0a9f1-106">[in] La dirección de memoria del que se obtienen `ppData`.</span><span class="sxs-lookup"><span data-stu-id="0a9f1-106">[in] The memory address from which to get `ppData`.</span></span>  
  
 `pcbData`  
 <span data-ttu-id="0a9f1-107">[out] Un puntero al tamaño, en bytes, de `ppData`.</span><span class="sxs-lookup"><span data-stu-id="0a9f1-107">[out] A pointer to the size, in bytes, of `ppData`.</span></span>  
  
 `ppData`  
 <span data-ttu-id="0a9f1-108">[out] Recupera un puntero a un puntero a los datos binarios.</span><span class="sxs-lookup"><span data-stu-id="0a9f1-108">[out] A pointer to a pointer to the binary data retrieved.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0a9f1-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0a9f1-109">Requirements</span></span>  
 <span data-ttu-id="0a9f1-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0a9f1-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0a9f1-111">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="0a9f1-111">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0a9f1-112">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0a9f1-112">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="0a9f1-113">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="0a9f1-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="0a9f1-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="0a9f1-114">See also</span></span>

- [<span data-ttu-id="0a9f1-115">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a9f1-115">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="0a9f1-116">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="0a9f1-116">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
