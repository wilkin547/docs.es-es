---
title: "IMetaDataTables::GetColumnInfo (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IMetaDataTables.GetColumnInfo
api_location: mscoree.dll
api_type: COM
f1_keywords: IMetaDataTables::GetColumnInfo
helpviewer_keywords:
- IMetaDataTables::GetColumnInfo method [.NET Framework metadata]
- GetColumnInfo method [.NET Framework metadata]
ms.assetid: 68c160ea-ae7d-4750-985d-a038b2c8e7d9
topic_type: apiref
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 939085294666a233341f65a8f5736d9dce201470
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="0d34a-102">IMetaDataTables::GetColumnInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="0d34a-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="0d34a-103">Obtiene datos sobre la columna especificada en la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="0d34a-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="0d34a-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0d34a-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="0d34a-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0d34a-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="0d34a-106">[in] El índice de la tabla deseada.</span><span class="sxs-lookup"><span data-stu-id="0d34a-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="0d34a-107">[in] El índice de la columna que desee.</span><span class="sxs-lookup"><span data-stu-id="0d34a-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="0d34a-108">[out] Un puntero al desplazamiento de la columna en la fila.</span><span class="sxs-lookup"><span data-stu-id="0d34a-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="0d34a-109">[out] Un puntero al tamaño, en bytes, de la columna.</span><span class="sxs-lookup"><span data-stu-id="0d34a-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="0d34a-110">[out] Un puntero al tipo de los valores de la columna.</span><span class="sxs-lookup"><span data-stu-id="0d34a-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="0d34a-111">[out] Un puntero a un puntero al nombre de columna.</span><span class="sxs-lookup"><span data-stu-id="0d34a-111">[out] A pointer to a pointer to the column name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="0d34a-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0d34a-112">Requirements</span></span>  
 <span data-ttu-id="0d34a-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0d34a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="0d34a-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="0d34a-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="0d34a-115">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="0d34a-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="0d34a-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="0d34a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0d34a-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="0d34a-117">See Also</span></span>  
 [<span data-ttu-id="0d34a-118">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d34a-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="0d34a-119">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="0d34a-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
