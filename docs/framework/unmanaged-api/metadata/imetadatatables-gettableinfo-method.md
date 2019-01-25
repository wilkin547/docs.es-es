---
title: IMetaDataTables::GetTableInfo (Método)
ms.date: 03/30/2017
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 9bf3e5d427698673576f71e290fde54275b75317
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54683461"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="510f4-102">IMetaDataTables::GetTableInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="510f4-102">IMetaDataTables::GetTableInfo Method</span></span>
<span data-ttu-id="510f4-103">Obtiene el nombre, el tamaño de fila, el número de filas, número de columnas y el índice de columna de clave de la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="510f4-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="510f4-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="510f4-104">Syntax</span></span>  
  
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
  
#### <a name="parameters"></a><span data-ttu-id="510f4-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="510f4-105">Parameters</span></span>  
 `ixTbl`  
 <span data-ttu-id="510f4-106">[in] El identificador de la tabla cuyas propiedades se deben devolver.</span><span class="sxs-lookup"><span data-stu-id="510f4-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="510f4-107">[out] Un puntero al tamaño, en bytes, de una fila de tabla.</span><span class="sxs-lookup"><span data-stu-id="510f4-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="510f4-108">[out] Un puntero al número de filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="510f4-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="510f4-109">[out] Un puntero al número de columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="510f4-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="510f4-110">[out] Un puntero al índice de la columna de clave, o -1 si la tabla no tiene ninguna columna de clave.</span><span class="sxs-lookup"><span data-stu-id="510f4-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="510f4-111">[out] Un puntero a un puntero al nombre de tabla.</span><span class="sxs-lookup"><span data-stu-id="510f4-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="510f4-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="510f4-112">Requirements</span></span>  
 <span data-ttu-id="510f4-113">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="510f4-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="510f4-114">**Encabezado**: Cor.h</span><span class="sxs-lookup"><span data-stu-id="510f4-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="510f4-115">**Biblioteca:** Usar como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="510f4-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="510f4-116">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="510f4-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="510f4-117">Vea también</span><span class="sxs-lookup"><span data-stu-id="510f4-117">See also</span></span>
- [<span data-ttu-id="510f4-118">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="510f4-118">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="510f4-119">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="510f4-119">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
