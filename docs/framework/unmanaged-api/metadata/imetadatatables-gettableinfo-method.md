---
title: "IMetaDataTables::GetTableInfo (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology:
- dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name:
- IMetaDataTables.GetTableInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetTableInfo
helpviewer_keywords:
- IMetaDataTables::GetTableInfo method [.NET Framework metadata]
- GetTableInfo method [.NET Framework metadata]
ms.assetid: 50cbe557-2322-41aa-8e0d-f967602eaa0f
topic_type:
- apiref
caps.latest.revision: 
author: mairaw
ms.author: mairaw
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 9ce9e3beb15724c7d7ddf02cbe7f83795d474139
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="2a760-102">IMetaDataTables::GetTableInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="2a760-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="2a760-103">Obtiene el nombre, el tamaño de fila, el número de filas, número de columnas y el índice de columna de clave de la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="2a760-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2a760-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2a760-104">Syntax</span></span>  
  
```  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="2a760-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2a760-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="2a760-106">[in] El identificador de la tabla cuyas propiedades se deben devolver.</span><span class="sxs-lookup"><span data-stu-id="2a760-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="2a760-107">[out] Un puntero al tamaño, en bytes, de una fila de tabla.</span><span class="sxs-lookup"><span data-stu-id="2a760-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="2a760-108">[out] Un puntero al número de filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2a760-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="2a760-109">[out] Un puntero al número de columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="2a760-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="2a760-110">[out] Un puntero al índice de la columna de clave, o -1 si la tabla no tiene ninguna columna de clave.</span><span class="sxs-lookup"><span data-stu-id="2a760-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="2a760-111">[out] Un puntero a un puntero al nombre de tabla.</span><span class="sxs-lookup"><span data-stu-id="2a760-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2a760-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2a760-112">Requirements</span></span>  
 <span data-ttu-id="2a760-113">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2a760-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a760-114">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="2a760-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="2a760-115">**Biblioteca:** usada como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="2a760-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="2a760-116">**Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a760-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a760-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="2a760-117">See Also</span></span>  
 [<span data-ttu-id="2a760-118">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2a760-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)  
 [<span data-ttu-id="2a760-119">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="2a760-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
