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
ms.openlocfilehash: 6156499368fb743b69c03f38b40ad3c5bcabce6e
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59174907"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="13711-102">IMetaDataTables::GetColumnInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="13711-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="13711-103">Obtiene datos sobre la columna especificada en la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="13711-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13711-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="13711-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="13711-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="13711-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="13711-106">[in] El índice de la tabla deseada.</span><span class="sxs-lookup"><span data-stu-id="13711-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="13711-107">[in] El índice de la columna que desee.</span><span class="sxs-lookup"><span data-stu-id="13711-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="13711-108">[out] Un puntero para el desplazamiento de la columna en la fila.</span><span class="sxs-lookup"><span data-stu-id="13711-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="13711-109">[out] Un puntero al tamaño, en bytes, de la columna.</span><span class="sxs-lookup"><span data-stu-id="13711-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="13711-110">[out] Un puntero al tipo de los valores de la columna.</span><span class="sxs-lookup"><span data-stu-id="13711-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="13711-111">[out] Un puntero a un puntero al nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="13711-111">[out] A pointer to a pointer to the column name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="13711-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="13711-112">Requirements</span></span>  
 <span data-ttu-id="13711-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="13711-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="13711-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="13711-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="13711-115">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="13711-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="13711-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="13711-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13711-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="13711-117">See also</span></span>

- [<span data-ttu-id="13711-118">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="13711-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="13711-119">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="13711-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
