---
title: IMetaDataTables (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataTables
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables
helpviewer_keywords:
- IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 31272cce-506a-4f18-bcbf-01ee45e36356
topic_type:
- apiref
ms.openlocfilehash: 073e73f082416308b893974471e39cbf5243d01c
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708860"
---
# <a name="imetadatatables-interface"></a><span data-ttu-id="dbf4d-102">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dbf4d-102">IMetaDataTables Interface</span></span>

<span data-ttu-id="dbf4d-103">Proporciona métodos para el almacenamiento y la recuperación de información de metadatos en tablas.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-103">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="dbf4d-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="dbf4d-104">Methods</span></span>  
  
|<span data-ttu-id="dbf4d-105">Método</span><span class="sxs-lookup"><span data-stu-id="dbf4d-105">Method</span></span>|<span data-ttu-id="dbf4d-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="dbf4d-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="dbf4d-107">Método GetBlob</span><span class="sxs-lookup"><span data-stu-id="dbf4d-107">GetBlob Method</span></span>](imetadatatables-getblob-method.md)|<span data-ttu-id="dbf4d-108">Obtiene un puntero al objeto binario grande (BLOB) en el índice de columna especificado.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-108">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>|  
|[<span data-ttu-id="dbf4d-109">Método GetBlobHeapSize</span><span class="sxs-lookup"><span data-stu-id="dbf4d-109">GetBlobHeapSize Method</span></span>](imetadatatables-getblobheapsize-method.md)|<span data-ttu-id="dbf4d-110">Obtiene el tamaño, en bytes, del montón de BLOBs.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-110">Gets the size, in bytes, of the BLOB heap.</span></span>|  
|[<span data-ttu-id="dbf4d-111">Método GetCodedTokenInfo</span><span class="sxs-lookup"><span data-stu-id="dbf4d-111">GetCodedTokenInfo Method</span></span>](imetadatatables-getcodedtokeninfo-method.md)|<span data-ttu-id="dbf4d-112">Obtiene un puntero a una matriz de tokens asociada al índice de fila especificado.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-112">Gets a pointer to an array of tokens associated with the specified row index.</span></span>|  
|[<span data-ttu-id="dbf4d-113">Método GetColumn</span><span class="sxs-lookup"><span data-stu-id="dbf4d-113">GetColumn Method</span></span>](imetadatatables-getcolumn-method.md)|<span data-ttu-id="dbf4d-114">Obtiene un puntero a los valores contenidos en la columna en el índice de columna especificado, en la tabla en el índice de tabla especificado.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-114">Gets a pointer to the values contained in the column at the specified column index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="dbf4d-115">Método GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="dbf4d-115">GetColumnInfo Method</span></span>](imetadatatables-getcolumninfo-method.md)|<span data-ttu-id="dbf4d-116">Obtiene datos sobre la columna especificada de la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-116">Gets data about the specified column in the specified table.</span></span>|  
|[<span data-ttu-id="dbf4d-117">Método GetGuid</span><span class="sxs-lookup"><span data-stu-id="dbf4d-117">GetGuid Method</span></span>](imetadatatables-getguid-method.md)|<span data-ttu-id="dbf4d-118">Obtiene un GUID de la fila en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-118">Gets a GUID from the row at the specified index.</span></span>|  
|[<span data-ttu-id="dbf4d-119">Método GetGuidHeapSize</span><span class="sxs-lookup"><span data-stu-id="dbf4d-119">GetGuidHeapSize Method</span></span>](imetadatatables-getguidheapsize-method.md)|<span data-ttu-id="dbf4d-120">Obtiene el tamaño, en bytes, del montón GUID.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-120">Gets the size, in bytes, of the GUID heap.</span></span>|  
|[<span data-ttu-id="dbf4d-121">Método GetNextBlob</span><span class="sxs-lookup"><span data-stu-id="dbf4d-121">GetNextBlob Method</span></span>](imetadatatables-getnextblob-method.md)|<span data-ttu-id="dbf4d-122">Obtiene el índice del siguiente BLOB de la tabla.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-122">Gets the index of the next BLOB in the table.</span></span>|  
|[<span data-ttu-id="dbf4d-123">Método GetNextGuid</span><span class="sxs-lookup"><span data-stu-id="dbf4d-123">GetNextGuid Method</span></span>](imetadatatables-getnextguid-method.md)|<span data-ttu-id="dbf4d-124">Obtiene el índice del siguiente valor de GUID en la columna de la tabla actual.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-124">Gets the index of the next GUID value in the current table column.</span></span>|  
|[<span data-ttu-id="dbf4d-125">Método GetNextString</span><span class="sxs-lookup"><span data-stu-id="dbf4d-125">GetNextString Method</span></span>](imetadatatables-getnextstring-method.md)|<span data-ttu-id="dbf4d-126">Obtiene el índice de la cadena siguiente en la columna de la tabla actual.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-126">Gets the index of the next string in the current table column.</span></span>|  
|[<span data-ttu-id="dbf4d-127">Método GetNextUserString</span><span class="sxs-lookup"><span data-stu-id="dbf4d-127">GetNextUserString Method</span></span>](imetadatatables-getnextuserstring-method.md)|<span data-ttu-id="dbf4d-128">Obtiene el índice de la fila que contiene la siguiente cadena codificada de forma rígida en la columna de la tabla actual.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-128">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>|  
|[<span data-ttu-id="dbf4d-129">Método GetNumTables</span><span class="sxs-lookup"><span data-stu-id="dbf4d-129">GetNumTables Method</span></span>](imetadatatables-getnumtables-method.md)|<span data-ttu-id="dbf4d-130">Obtiene el número de tablas en el ámbito de la `IMetaDataTables` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-130">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>|  
|[<span data-ttu-id="dbf4d-131">Método GetRow</span><span class="sxs-lookup"><span data-stu-id="dbf4d-131">GetRow Method</span></span>](imetadatatables-getrow-method.md)|<span data-ttu-id="dbf4d-132">Obtiene la fila en el índice de fila especificado de la tabla en el índice de tabla especificado.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-132">Gets the row at the specified row index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="dbf4d-133">GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="dbf4d-133">GetString Method</span></span>](imetadatatables-getstring-method.md)|<span data-ttu-id="dbf4d-134">Obtiene la cadena en el índice especificado de la columna de tabla del ámbito de referencia actual.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-134">Gets the string at the specified index from the table column in the current reference scope.</span></span>|  
|[<span data-ttu-id="dbf4d-135">Método GetStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="dbf4d-135">GetStringHeapSize Method</span></span>](imetadatatables-getstringheapsize-method.md)|<span data-ttu-id="dbf4d-136">Obtiene el tamaño, en bytes, del montón de cadenas.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-136">Gets the size, in bytes, of the string heap.</span></span>|  
|[<span data-ttu-id="dbf4d-137">Método GetTableIndex</span><span class="sxs-lookup"><span data-stu-id="dbf4d-137">GetTableIndex Method</span></span>](imetadatatables-gettableindex-method.md)|<span data-ttu-id="dbf4d-138">Obtiene el índice de la tabla a la que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-138">Gets the index for the table referenced by the specified token.</span></span>|  
|[<span data-ttu-id="dbf4d-139">Método GetTableInfo</span><span class="sxs-lookup"><span data-stu-id="dbf4d-139">GetTableInfo Method</span></span>](imetadatatables-gettableinfo-method.md)|<span data-ttu-id="dbf4d-140">Obtiene el nombre, el tamaño de la fila, el número de filas, el número de columnas y el índice de columna de clave de la tabla en el índice de tabla especificado.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-140">Gets the name, row size, number of rows, number of columns, and key column index of the table at the specified table index.</span></span>|  
|[<span data-ttu-id="dbf4d-141">Método GetUserString</span><span class="sxs-lookup"><span data-stu-id="dbf4d-141">GetUserString Method</span></span>](imetadatatables-getuserstring-method.md)|<span data-ttu-id="dbf4d-142">Obtiene la cadena codificada de forma rígida en el índice especificado de la columna de cadena en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-142">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>|  
|[<span data-ttu-id="dbf4d-143">Método GetUserStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="dbf4d-143">GetUserStringHeapSize Method</span></span>](imetadatatables-getuserstringheapsize-method.md)|<span data-ttu-id="dbf4d-144">Obtiene el tamaño, en bytes, del montón de cadena de usuario.</span><span class="sxs-lookup"><span data-stu-id="dbf4d-144">Gets the size, in bytes, of the user string heap.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="dbf4d-145">Requisitos</span><span class="sxs-lookup"><span data-stu-id="dbf4d-145">Requirements</span></span>  

 <span data-ttu-id="dbf4d-146">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="dbf4d-146">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="dbf4d-147">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="dbf4d-147">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="dbf4d-148">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="dbf4d-148">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="dbf4d-149">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="dbf4d-149">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="dbf4d-150">Consulte también</span><span class="sxs-lookup"><span data-stu-id="dbf4d-150">See also</span></span>

- [<span data-ttu-id="dbf4d-151">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="dbf4d-151">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="dbf4d-152">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="dbf4d-152">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
