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
ms.openlocfilehash: 2105033e684ec172e24adfb14bcab7668b388af3
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501126"
---
# <a name="imetadatatables-interface"></a><span data-ttu-id="daa98-102">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="daa98-102">IMetaDataTables Interface</span></span>
<span data-ttu-id="daa98-103">Proporciona métodos para el almacenamiento y la recuperación de información de metadatos en tablas.</span><span class="sxs-lookup"><span data-stu-id="daa98-103">Provides methods for the storage and retrieval of metadata information in tables.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="daa98-104">Métodos</span><span class="sxs-lookup"><span data-stu-id="daa98-104">Methods</span></span>  
  
|<span data-ttu-id="daa98-105">Método</span><span class="sxs-lookup"><span data-stu-id="daa98-105">Method</span></span>|<span data-ttu-id="daa98-106">Descripción</span><span class="sxs-lookup"><span data-stu-id="daa98-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="daa98-107">Método GetBlob</span><span class="sxs-lookup"><span data-stu-id="daa98-107">GetBlob Method</span></span>](imetadatatables-getblob-method.md)|<span data-ttu-id="daa98-108">Obtiene un puntero al objeto binario grande (BLOB) en el índice de columna especificado.</span><span class="sxs-lookup"><span data-stu-id="daa98-108">Gets a pointer to the binary large object (BLOB) at the specified column index.</span></span>|  
|[<span data-ttu-id="daa98-109">Método GetBlobHeapSize</span><span class="sxs-lookup"><span data-stu-id="daa98-109">GetBlobHeapSize Method</span></span>](imetadatatables-getblobheapsize-method.md)|<span data-ttu-id="daa98-110">Obtiene el tamaño, en bytes, del montón de BLOBs.</span><span class="sxs-lookup"><span data-stu-id="daa98-110">Gets the size, in bytes, of the BLOB heap.</span></span>|  
|[<span data-ttu-id="daa98-111">Método GetCodedTokenInfo</span><span class="sxs-lookup"><span data-stu-id="daa98-111">GetCodedTokenInfo Method</span></span>](imetadatatables-getcodedtokeninfo-method.md)|<span data-ttu-id="daa98-112">Obtiene un puntero a una matriz de tokens asociada al índice de fila especificado.</span><span class="sxs-lookup"><span data-stu-id="daa98-112">Gets a pointer to an array of tokens associated with the specified row index.</span></span>|  
|[<span data-ttu-id="daa98-113">Método GetColumn</span><span class="sxs-lookup"><span data-stu-id="daa98-113">GetColumn Method</span></span>](imetadatatables-getcolumn-method.md)|<span data-ttu-id="daa98-114">Obtiene un puntero a los valores contenidos en la columna en el índice de columna especificado, en la tabla en el índice de tabla especificado.</span><span class="sxs-lookup"><span data-stu-id="daa98-114">Gets a pointer to the values contained in the column at the specified column index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="daa98-115">Método GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="daa98-115">GetColumnInfo Method</span></span>](imetadatatables-getcolumninfo-method.md)|<span data-ttu-id="daa98-116">Obtiene datos sobre la columna especificada de la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="daa98-116">Gets data about the specified column in the specified table.</span></span>|  
|[<span data-ttu-id="daa98-117">Método GetGuid</span><span class="sxs-lookup"><span data-stu-id="daa98-117">GetGuid Method</span></span>](imetadatatables-getguid-method.md)|<span data-ttu-id="daa98-118">Obtiene un GUID de la fila en el índice especificado.</span><span class="sxs-lookup"><span data-stu-id="daa98-118">Gets a GUID from the row at the specified index.</span></span>|  
|[<span data-ttu-id="daa98-119">Método GetGuidHeapSize</span><span class="sxs-lookup"><span data-stu-id="daa98-119">GetGuidHeapSize Method</span></span>](imetadatatables-getguidheapsize-method.md)|<span data-ttu-id="daa98-120">Obtiene el tamaño, en bytes, del montón GUID.</span><span class="sxs-lookup"><span data-stu-id="daa98-120">Gets the size, in bytes, of the GUID heap.</span></span>|  
|[<span data-ttu-id="daa98-121">Método GetNextBlob</span><span class="sxs-lookup"><span data-stu-id="daa98-121">GetNextBlob Method</span></span>](imetadatatables-getnextblob-method.md)|<span data-ttu-id="daa98-122">Obtiene el índice del siguiente BLOB de la tabla.</span><span class="sxs-lookup"><span data-stu-id="daa98-122">Gets the index of the next BLOB in the table.</span></span>|  
|[<span data-ttu-id="daa98-123">Método GetNextGuid</span><span class="sxs-lookup"><span data-stu-id="daa98-123">GetNextGuid Method</span></span>](imetadatatables-getnextguid-method.md)|<span data-ttu-id="daa98-124">Obtiene el índice del siguiente valor de GUID en la columna de la tabla actual.</span><span class="sxs-lookup"><span data-stu-id="daa98-124">Gets the index of the next GUID value in the current table column.</span></span>|  
|[<span data-ttu-id="daa98-125">Método GetNextString</span><span class="sxs-lookup"><span data-stu-id="daa98-125">GetNextString Method</span></span>](imetadatatables-getnextstring-method.md)|<span data-ttu-id="daa98-126">Obtiene el índice de la cadena siguiente en la columna de la tabla actual.</span><span class="sxs-lookup"><span data-stu-id="daa98-126">Gets the index of the next string in the current table column.</span></span>|  
|[<span data-ttu-id="daa98-127">Método GetNextUserString</span><span class="sxs-lookup"><span data-stu-id="daa98-127">GetNextUserString Method</span></span>](imetadatatables-getnextuserstring-method.md)|<span data-ttu-id="daa98-128">Obtiene el índice de la fila que contiene la siguiente cadena codificada de forma rígida en la columna de la tabla actual.</span><span class="sxs-lookup"><span data-stu-id="daa98-128">Gets the index of the row that contains the next hard-coded string in the current table column.</span></span>|  
|[<span data-ttu-id="daa98-129">Método GetNumTables</span><span class="sxs-lookup"><span data-stu-id="daa98-129">GetNumTables Method</span></span>](imetadatatables-getnumtables-method.md)|<span data-ttu-id="daa98-130">Obtiene el número de tablas en el ámbito de la `IMetaDataTables` instancia actual.</span><span class="sxs-lookup"><span data-stu-id="daa98-130">Gets the number of tables in the scope of the current `IMetaDataTables` instance.</span></span>|  
|[<span data-ttu-id="daa98-131">Método GetRow</span><span class="sxs-lookup"><span data-stu-id="daa98-131">GetRow Method</span></span>](imetadatatables-getrow-method.md)|<span data-ttu-id="daa98-132">Obtiene la fila en el índice de fila especificado de la tabla en el índice de tabla especificado.</span><span class="sxs-lookup"><span data-stu-id="daa98-132">Gets the row at the specified row index, in the table at the specified table index.</span></span>|  
|[<span data-ttu-id="daa98-133">GetString (Método)</span><span class="sxs-lookup"><span data-stu-id="daa98-133">GetString Method</span></span>](imetadatatables-getstring-method.md)|<span data-ttu-id="daa98-134">Obtiene la cadena en el índice especificado de la columna de tabla del ámbito de referencia actual.</span><span class="sxs-lookup"><span data-stu-id="daa98-134">Gets the string at the specified index from the table column in the current reference scope.</span></span>|  
|[<span data-ttu-id="daa98-135">Método GetStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="daa98-135">GetStringHeapSize Method</span></span>](imetadatatables-getstringheapsize-method.md)|<span data-ttu-id="daa98-136">Obtiene el tamaño, en bytes, del montón de cadenas.</span><span class="sxs-lookup"><span data-stu-id="daa98-136">Gets the size, in bytes, of the string heap.</span></span>|  
|[<span data-ttu-id="daa98-137">Método GetTableIndex</span><span class="sxs-lookup"><span data-stu-id="daa98-137">GetTableIndex Method</span></span>](imetadatatables-gettableindex-method.md)|<span data-ttu-id="daa98-138">Obtiene el índice de la tabla a la que hace referencia el token especificado.</span><span class="sxs-lookup"><span data-stu-id="daa98-138">Gets the index for the table referenced by the specified token.</span></span>|  
|[<span data-ttu-id="daa98-139">Método GetTableInfo</span><span class="sxs-lookup"><span data-stu-id="daa98-139">GetTableInfo Method</span></span>](imetadatatables-gettableinfo-method.md)|<span data-ttu-id="daa98-140">Obtiene el nombre, el tamaño de la fila, el número de filas, el número de columnas y el índice de columna de clave de la tabla en el índice de tabla especificado.</span><span class="sxs-lookup"><span data-stu-id="daa98-140">Gets the name, row size, number of rows, number of columns, and key column index of the table at the specified table index.</span></span>|  
|[<span data-ttu-id="daa98-141">Método GetUserString</span><span class="sxs-lookup"><span data-stu-id="daa98-141">GetUserString Method</span></span>](imetadatatables-getuserstring-method.md)|<span data-ttu-id="daa98-142">Obtiene la cadena codificada de forma rígida en el índice especificado de la columna de cadena en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="daa98-142">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>|  
|[<span data-ttu-id="daa98-143">Método GetUserStringHeapSize</span><span class="sxs-lookup"><span data-stu-id="daa98-143">GetUserStringHeapSize Method</span></span>](imetadatatables-getuserstringheapsize-method.md)|<span data-ttu-id="daa98-144">Obtiene el tamaño, en bytes, del montón de cadena de usuario.</span><span class="sxs-lookup"><span data-stu-id="daa98-144">Gets the size, in bytes, of the user string heap.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="daa98-145">Requisitos</span><span class="sxs-lookup"><span data-stu-id="daa98-145">Requirements</span></span>  
 <span data-ttu-id="daa98-146">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="daa98-146">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="daa98-147">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="daa98-147">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="daa98-148">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="daa98-148">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="daa98-149">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="daa98-149">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="daa98-150">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="daa98-150">See also</span></span>

- [<span data-ttu-id="daa98-151">Interfaces de metadatos</span><span class="sxs-lookup"><span data-stu-id="daa98-151">Metadata Interfaces</span></span>](metadata-interfaces.md)
- [<span data-ttu-id="daa98-152">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="daa98-152">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
