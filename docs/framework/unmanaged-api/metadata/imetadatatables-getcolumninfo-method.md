---
title: IMetaDataTables::GetColumnInfo (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetColumnInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetColumnInfo
helpviewer_keywords:
- IMetaDataTables::GetColumnInfo method [.NET Framework metadata]
- GetColumnInfo method [.NET Framework metadata]
ms.assetid: 68c160ea-ae7d-4750-985d-a038b2c8e7d9
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: bcab5adf30648f6b5a614a407478977bc37c7062
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57480707"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="89581-102">IMetaDataTables::GetColumnInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="89581-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="89581-103">Obtiene datos sobre la columna especificada en la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="89581-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="89581-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="89581-104">Syntax</span></span>  
  
```  
HRESULT GetColumnInfo (   
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="89581-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="89581-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="89581-106">[in] El índice de la tabla deseada.</span><span class="sxs-lookup"><span data-stu-id="89581-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="89581-107">[in] El índice de la columna que desee.</span><span class="sxs-lookup"><span data-stu-id="89581-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="89581-108">[out] Un puntero para el desplazamiento de la columna en la fila.</span><span class="sxs-lookup"><span data-stu-id="89581-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="89581-109">[out] Un puntero al tamaño, en bytes, de la columna.</span><span class="sxs-lookup"><span data-stu-id="89581-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="89581-110">[out] Un puntero al tipo de los valores de la columna.</span><span class="sxs-lookup"><span data-stu-id="89581-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="89581-111">[out] Un puntero a un puntero al nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="89581-111">[out] A pointer to a pointer to the column name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="89581-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="89581-112">Requirements</span></span>  
 <span data-ttu-id="89581-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="89581-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="89581-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="89581-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="89581-115">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="89581-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="89581-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="89581-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="89581-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="89581-117">See also</span></span>
- [<span data-ttu-id="89581-118">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="89581-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="89581-119">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="89581-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
