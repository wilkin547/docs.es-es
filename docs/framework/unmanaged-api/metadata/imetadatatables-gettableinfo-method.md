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
ms.openlocfilehash: 65943ac169106a95feaff7d44017444e65764b60
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95672544"
---
# <a name="imetadatatablesgettableinfo-method"></a><span data-ttu-id="ac5fe-102">IMetaDataTables::GetTableInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="ac5fe-102">IMetaDataTables::GetTableInfo Method</span></span>

<span data-ttu-id="ac5fe-103">Obtiene el nombre, el tamaño de la fila, el número de filas, el número de columnas y el índice de la columna de clave de la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-103">Gets the name, row size, number of rows, number of columns, and key column index of the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ac5fe-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ac5fe-104">Syntax</span></span>  
  
```cpp  
HRESULT GetTableInfo (  
    [in]  ULONG       ixTbl,  
    [out] ULONG       *pcbRow,  
    [out] ULONG       *pcRows,  
    [out] ULONG       *pcCols,  
    [out] ULONG       *piKey,  
    [out] const char  **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ac5fe-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ac5fe-105">Parameters</span></span>  

 `ixTbl`  
 <span data-ttu-id="ac5fe-106">de Identificador de la tabla cuyas propiedades se van a devolver.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-106">[in] The identifier of the table whose properties to return.</span></span>  
  
 `pcbRow`  
 <span data-ttu-id="ac5fe-107">enuncia Puntero al tamaño, en bytes, de una fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-107">[out] A pointer to the size, in bytes, of a table row.</span></span>  
  
 `pcRows`  
 <span data-ttu-id="ac5fe-108">enuncia Puntero al número de filas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-108">[out] A pointer to the number of rows in the table.</span></span>  
  
 `pcCols`  
 <span data-ttu-id="ac5fe-109">enuncia Puntero al número de columnas de la tabla.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-109">[out] A pointer to the number of columns in the table.</span></span>  
  
 `piKey`  
 <span data-ttu-id="ac5fe-110">enuncia Puntero al índice de la columna de clave o-1 si la tabla no tiene ninguna columna de clave.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-110">[out] A pointer to the index of the key column, or -1 if the table has no key column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="ac5fe-111">enuncia Un puntero a un puntero al nombre de la tabla.</span><span class="sxs-lookup"><span data-stu-id="ac5fe-111">[out] A pointer to a pointer to the table name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ac5fe-112">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ac5fe-112">Requirements</span></span>  

 <span data-ttu-id="ac5fe-113">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ac5fe-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ac5fe-114">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="ac5fe-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ac5fe-115">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ac5fe-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ac5fe-116">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ac5fe-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ac5fe-117">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ac5fe-117">See also</span></span>

- [<span data-ttu-id="ac5fe-118">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac5fe-118">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="ac5fe-119">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="ac5fe-119">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
