---
description: 'Más información acerca de: IMetaDataTables (interfaz)'
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
ms.openlocfilehash: c3edf504586bad1252c36d6e8254193eaf9cc26d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799278"
---
# <a name="imetadatatables-interface"></a><span data-ttu-id="c0ce3-103">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c0ce3-103">IMetaDataTables Interface</span></span>

<span data-ttu-id="c0ce3-104">Proporciona métodos para el almacenamiento y la recuperación de información de metadatos en tablas.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-104">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="c0ce3-105">Métodos</span><span class="sxs-lookup"><span data-stu-id="c0ce3-105">Methods</span></span>  
  
|<span data-ttu-id="c0ce3-106">Método</span><span class="sxs-lookup"><span data-stu-id="c0ce3-106">Method</span></span>|<span data-ttu-id="c0ce3-107">Descripción</span><span class="sxs-lookup"><span data-stu-id="c0ce3-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="c0ce3-108">Método GetBlob</span><span class="sxs-lookup"><span data-stu-id="c0ce3-108">GetBlob Method</span></span>](imetadatatables-getblob-method.md)|<span data-ttu-id="c0ce3-109">Obtiene un puntero al objeto binario grande (BLOB) en el índice de columna especificado.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-109">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>|  
|[<span data-ttu-id="c0ce3-110">Método GetBlobHeapSize</span><span class="sxs-lookup"><span data-stu-id="c0ce3-110">GetBlobHeapSize Method</span></span>](imetadatatables-getblobheapsize-method.md)|<span data-ttu-id="c0ce3-111">Obtiene el tamaño, en bytes, del montón de BLOBs.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-111">Gets the size, in bytes, of the BLOB heap.</span></span>|  
|[<span data-ttu-id="c0ce3-112">Método GetCodedTokenInfo</span><span class="sxs-lookup"><span data-stu-id="c0ce3-112">GetCodedTokenInfo Method</span></span>](imetadatatables-getcodedtokeninfo-method.md)|<span data-ttu-id="c0ce3-113">Obtiene un puntero a una matriz de tokens asociada al índice de fila especificado.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-113">Gets a pointer to an array of tokens associated with the specified row index.</span></span>|  
|[<span data-ttu-id="c0ce3-114">Método GetColumn</span><span class="sxs-lookup"><span data-stu-id="c0ce3-114">GetColumn Method</span></span>](imetadatatables-getcolumn-method.md)|<span data-ttu-id="c0ce3-115">Obtiene un puntero a los valores contenidos en la columna en el índice de columna especificado, en la tabla en el índice de tabla especificado.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-115">Gets a pointer to the values contained in the column at the specified column index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="c0ce3-116">Método GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="c0ce3-116">GetColumnInfo Method</span></span>](imetadatatables-getcolumninfo-method.md)|<span data-ttu-id="c0ce3-117">Obtiene datos sobre la columna especificada de la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-117">Gets data about the specified column in the specified table.</span></span>|  
|[<span data-ttu-id="c0ce3-118">Método GetGuid</span><span class="sxs-lookup"><span data-stu-id="c0ce3-118">GetGuid Method</span></span>](imetadatatables-getguid-method.md)|<span data-ttu-id="c0ce3-119">Obtiene un GUID de la fila en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-119">Gets a GUID from the row at the specified index.</span></span>|  
|[<span data-ttu-id="c0ce3-120">Método GetGuidHeapSize</span><span class="sxs-lookup"><span data-stu-id="c0ce3-120">GetGuidHeapSize Method</span></span>](imetadatatables-getguidheapsize-method.md)|<span data-ttu-id="c0ce3-121">Obtiene el tamaño, en bytes, del montón GUID.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-121">Gets the size, in bytes, of the GUID heap.</span></span>|  
|[<span data-ttu-id="c0ce3-122">Método GetNextBlob</span><span class="sxs-lookup"><span data-stu-id="c0ce3-122">GetNextBlob Method</span></span>](imetadatatables-getnextblob-method.md)|<span data-ttu-id="c0ce3-123">Obtiene el índice del siguiente BLOB de la tabla.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-123">Gets the index of the next BLOB in the table.</span></span>|  
|[<span data-ttu-id="c0ce3-124">Método GetNextGuid</span><span class="sxs-lookup"><span data-stu-id="c0ce3-124">GetNextGuid Method</span></span>](imetadatatables-getnextguid-method.md)|<span data-ttu-id="c0ce3-125">Obtiene el índice del siguiente valor de GUID en la columna de la tabla actual.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-125">Gets the index of the next GUID value in the current table column.</span></span>|  
|[<span data-ttu-id="c0ce3-126">Método GetNextString</span><span class="sxs-lookup"><span data-stu-id="c0ce3-126">GetNextString Method</span></span>](imetadatatables-getnextstring-method.md)|<span data-ttu-id="c0ce3-127">Obtiene el índice de la cadena siguiente en la columna de la tabla actual.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-127">Gets the index of the next string in the current table column.</span></span>|  
|[<span data-ttu-id="c0ce3-128">Método GetNextUserString</span><span class="sxs-lookup"><span data-stu-id="c0ce3-128">GetNextUserString Method</span></span>](imetadatatables-getnextuserstring-method.md)|<span data-ttu-id="c0ce3-129">Obtiene el índice de la fila que contiene la siguiente cadena codificada de forma rígida en la columna de la tabla actual.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-129">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>|  
|[<span data-ttu-id="c0ce3-130">Método GetNumTables</span><span class="sxs-lookup"><span data-stu-id="c0ce3-130">GetNumTables Method</span></span>](imetadatatables-getnumtables-method.md)|<span data-ttu-id="c0ce3-131">Obtiene el número de tablas en el ámbito de la `IMetaDataTables` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-131">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>|  
|[<span data-ttu-id="c0ce3-132">Método GetRow</span><span class="sxs-lookup"><span data-stu-id="c0ce3-132">GetRow Method</span></span>](imetadatatables-getrow-method.md)|<span data-ttu-id="c0ce3-133">Obtiene la fila en el índice de fila especificado de la tabla en el índice de tabla especificado.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-133">Gets the row at the specified row index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="c0ce3-134">GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="c0ce3-134">GetString Method</span></span>](imetadatatables-getstring-method.md)|<span data-ttu-id="c0ce3-135">Obtiene la cadena en el índice especificado de la columna de tabla del ámbito de referencia actual.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-135">Gets the string at the specified index from the table column in the current reference scope.</span></span>|  
|[<span data-ttu-id="c0ce3-136">Método GetStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="c0ce3-136">GetStringHeapSize Method</span></span>](imetadatatables-getstringheapsize-method.md)|<span data-ttu-id="c0ce3-137">Obtiene el tamaño, en bytes, del montón de cadenas.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-137">Gets the size, in bytes, of the string heap.</span></span>|  
|[<span data-ttu-id="c0ce3-138">Método GetTableIndex</span><span class="sxs-lookup"><span data-stu-id="c0ce3-138">GetTableIndex Method</span></span>](imetadatatables-gettableindex-method.md)|<span data-ttu-id="c0ce3-139">Obtiene el índice de la tabla a la que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-139">Gets the index for the table referenced by the specified token.</span></span>|  
|[<span data-ttu-id="c0ce3-140">Método GetTableInfo</span><span class="sxs-lookup"><span data-stu-id="c0ce3-140">GetTableInfo Method</span></span>](imetadatatables-gettableinfo-method.md)|<span data-ttu-id="c0ce3-141">Obtiene el nombre, el tamaño de la fila, el número de filas, el número de columnas y el índice de columna de clave de la tabla en el índice de tabla especificado.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-141">Gets the name, row size, number of rows, number of columns, and key column index of the table at the specified table index.</span></span>|  
|[<span data-ttu-id="c0ce3-142">Método GetUserString</span><span class="sxs-lookup"><span data-stu-id="c0ce3-142">GetUserString Method</span></span>](imetadatatables-getuserstring-method.md)|<span data-ttu-id="c0ce3-143">Obtiene la cadena codificada de forma rígida en el índice especificado de la columna de cadena en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-143">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>|  
|[<span data-ttu-id="c0ce3-144">Método GetUserStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="c0ce3-144">GetUserStringHeapSize Method</span></span>](imetadatatables-getuserstringheapsize-method.md)|<span data-ttu-id="c0ce3-145">Obtiene el tamaño, en bytes, del montón de cadena de usuario.</span><span class="sxs-lookup"><span data-stu-id="c0ce3-145">Gets the size, in bytes, of the user string heap.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c0ce3-146">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c0ce3-146">Requirements</span></span>  

 <span data-ttu-id="c0ce3-147">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c0ce3-147">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="c0ce3-148">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="c0ce3-148">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="c0ce3-149">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c0ce3-149">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="c0ce3-150">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c0ce3-150">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c0ce3-151">Vea también</span><span class="sxs-lookup"><span data-stu-id="c0ce3-151">See also</span></span>

- [<span data-ttu-id="c0ce3-152">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="c0ce3-152">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="c0ce3-153">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="c0ce3-153">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
