---
title: IMetaDataTables::GetNextString (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetNextString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetNextString
helpviewer_keywords:
- IMetaDataTables::GetNextString method [.NET Framework metadata]
- GetNextString method [.NET Framework metadata]
ms.assetid: d9720428-c353-4f07-a7e8-899e106a1b37
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4e7e7d89f4c994c5ce37dc09d15826185ed1bb25
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59129381"
---
# <a name="imetadatatablesgetnextstring-method"></a><span data-ttu-id="e8db4-102">IMetaDataTables::GetNextString (Método)</span><span class="sxs-lookup"><span data-stu-id="e8db4-102">IMetaDataTables::GetNextString Method</span></span>
<span data-ttu-id="e8db4-103">Obtiene el índice de la cadena siguiente en la columna de tabla actual.</span><span class="sxs-lookup"><span data-stu-id="e8db4-103">Gets the index of the next string in the current table column.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e8db4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8db4-104">Syntax</span></span>  
  
```  
HRESULT GetNextString (   
    [in]  ULONG   ixString,  
    [out] ULONG   *pNext  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e8db4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e8db4-105">Parameters</span></span>  
 `ixString`  
 <span data-ttu-id="e8db4-106">[in] El valor de índice de una columna de tabla de cadenas.</span><span class="sxs-lookup"><span data-stu-id="e8db4-106">[in] The index value from a string table column.</span></span>  
  
 `pNext`  
 <span data-ttu-id="e8db4-107">[out] Un puntero al índice de la cadena siguiente en la columna.</span><span class="sxs-lookup"><span data-stu-id="e8db4-107">[out] A pointer to the index of the next string in the column.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e8db4-108">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8db4-108">Requirements</span></span>  
 <span data-ttu-id="e8db4-109">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8db4-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8db4-110">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="e8db4-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="e8db4-111">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="e8db4-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 **<span data-ttu-id="e8db4-112">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="e8db4-112">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e8db4-113">Vea también</span><span class="sxs-lookup"><span data-stu-id="e8db4-113">See also</span></span>

- [<span data-ttu-id="e8db4-114">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8db4-114">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="e8db4-115">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="e8db4-115">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
