---
title: IMetaDataTables::GetColumn (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetColumn
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumn
helpviewer_keywords:
- IMetaDataTables::GetColumn method [.NET Framework metadata]
- GetColumn method [.NET Framework metadata]
ms.assetid: 1032055b-cabb-45c5-a50e-7e853201b175
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 90ce56b3959c4768ef9cb6a9c551d53c5300a39e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59208363"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="cc996-102">IMetaDataTables::GetColumn (Método)</span><span class="sxs-lookup"><span data-stu-id="cc996-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="cc996-103">Obtiene un puntero al valor incluido en la celda de la columna especificada y la fila en la tabla dada.</span><span class="sxs-lookup"><span data-stu-id="cc996-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc996-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="cc996-104">Syntax</span></span>  
  
```  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc996-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="cc996-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="cc996-106">[in] El índice de la tabla.</span><span class="sxs-lookup"><span data-stu-id="cc996-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="cc996-107">[in] El índice de la columna en la tabla.</span><span class="sxs-lookup"><span data-stu-id="cc996-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="cc996-108">[in] El índice de la fila en la tabla.</span><span class="sxs-lookup"><span data-stu-id="cc996-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="cc996-109">[out] Un puntero al valor de la celda.</span><span class="sxs-lookup"><span data-stu-id="cc996-109">[out] A pointer to the value in the cell.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="cc996-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="cc996-110">Requirements</span></span>  
 <span data-ttu-id="cc996-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="cc996-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="cc996-112">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="cc996-112">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="cc996-113">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="cc996-113">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="cc996-114">**Versiones de .NET framework** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="cc996-114">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cc996-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="cc996-115">See also</span></span>

- [<span data-ttu-id="cc996-116">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cc996-116">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="cc996-117">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="cc996-117">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
