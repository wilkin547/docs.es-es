---
description: 'Más información acerca de: IMetaDataTables:: Getcolumn ((método)'
title: IMetaDataTables::GetColumn (Método)
ms.date: 02/25/2019
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
ms.openlocfilehash: 4c4cec7216f93783b34b594330358d1e6036ed40
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688278"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="1e4e8-103">IMetaDataTables::GetColumn (Método)</span><span class="sxs-lookup"><span data-stu-id="1e4e8-103">IMetaDataTables::GetColumn Method</span></span>

<span data-ttu-id="1e4e8-104">Obtiene un puntero al valor contenido en la celda de la columna y la fila especificadas en la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-104">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e4e8-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1e4e8-105">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e4e8-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1e4e8-106">Parameters</span></span>

 `ixTbl`  
 <span data-ttu-id="1e4e8-107">de Índice de la tabla.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-107">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="1e4e8-108">de Índice de la columna de la tabla.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-108">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="1e4e8-109">de Índice de la fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-109">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="1e4e8-110">enuncia Puntero al valor de la celda.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-110">[out] A pointer to the value in the cell.</span></span>  

## <a name="remarks"></a><span data-ttu-id="1e4e8-111">Observaciones</span><span class="sxs-lookup"><span data-stu-id="1e4e8-111">Remarks</span></span>

<span data-ttu-id="1e4e8-112">La interpretación del valor devuelto a través `pVal` de depende del tipo de la columna.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-112">The interpretion of the value returned through `pVal` depends on the column's type.</span></span> <span data-ttu-id="1e4e8-113">El tipo de columna se puede determinar mediante una llamada a [IMetaDataTables. GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="1e4e8-113">The column type can be determined by calling [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span></span>

- <span data-ttu-id="1e4e8-114">El método **getcolumn (** convierte automáticamente las columnas de tipo **RID** o **CodedToken** a valores completos de 32 bits `mdToken` .</span><span class="sxs-lookup"><span data-stu-id="1e4e8-114">The **GetColumn** method automatically converts columns of type **Rid** or **CodedToken** to full 32-bit `mdToken` values.</span></span>
- <span data-ttu-id="1e4e8-115">También convierte automáticamente los valores de 8 o 16 bits en valores completos de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-115">It also automatically converts 8-bit or 16-bit values to full 32-bit values.</span></span>
- <span data-ttu-id="1e4e8-116">En el caso de las columnas de tipo de *montón* , el *pval* devuelto será un índice en el montón correspondiente.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-116">For *heap* type columns, the returned *pVal* will be an index into the corresponding heap.</span></span>

| <span data-ttu-id="1e4e8-117">Tipo de columna</span><span class="sxs-lookup"><span data-stu-id="1e4e8-117">Column type</span></span>              | <span data-ttu-id="1e4e8-118">pVal contiene</span><span class="sxs-lookup"><span data-stu-id="1e4e8-118">pVal contains</span></span> | <span data-ttu-id="1e4e8-119">Comentario</span><span class="sxs-lookup"><span data-stu-id="1e4e8-119">Comment</span></span>                          |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="1e4e8-120">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="1e4e8-120">`0`..`iRidMax`</span></span><br><span data-ttu-id="1e4e8-121">(0.. 63)</span><span class="sxs-lookup"><span data-stu-id="1e4e8-121">(0..63)</span></span>  | <span data-ttu-id="1e4e8-122">mdToken</span><span class="sxs-lookup"><span data-stu-id="1e4e8-122">mdToken</span></span>     | <span data-ttu-id="1e4e8-123">*pval* contendrá un token completo.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-123">*pVal* will contain a full Token.</span></span> <span data-ttu-id="1e4e8-124">La función convierte automáticamente el RID en un token completo.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-124">The function automatically converts the Rid into a full token.</span></span> |
| <span data-ttu-id="1e4e8-125">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="1e4e8-125">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="1e4e8-126">(64.. 95)</span><span class="sxs-lookup"><span data-stu-id="1e4e8-126">(64..95)</span></span> | <span data-ttu-id="1e4e8-127">mdToken</span><span class="sxs-lookup"><span data-stu-id="1e4e8-127">mdToken</span></span> | <span data-ttu-id="1e4e8-128">Después de la devolución, *pval* contendrá un token completo.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-128">Upon return, *pVal* will contain a full Token.</span></span> <span data-ttu-id="1e4e8-129">La función descomprime automáticamente CodedToken en un token completo.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-129">The function automatically decompresses the CodedToken into a full token.</span></span> |
| <span data-ttu-id="1e4e8-130">`iSHORT` (96)</span><span class="sxs-lookup"><span data-stu-id="1e4e8-130">`iSHORT` (96)</span></span>            | <span data-ttu-id="1e4e8-131">Int16</span><span class="sxs-lookup"><span data-stu-id="1e4e8-131">Int16</span></span>         | <span data-ttu-id="1e4e8-132">El signo se extiende automáticamente a 32 bits.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-132">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="1e4e8-133">`iUSHORT` (97)</span><span class="sxs-lookup"><span data-stu-id="1e4e8-133">`iUSHORT` (97)</span></span>           | <span data-ttu-id="1e4e8-134">UInt16</span><span class="sxs-lookup"><span data-stu-id="1e4e8-134">UInt16</span></span>        | <span data-ttu-id="1e4e8-135">El signo se extiende automáticamente a 32 bits.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-135">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="1e4e8-136">`iLONG` (98)</span><span class="sxs-lookup"><span data-stu-id="1e4e8-136">`iLONG` (98)</span></span>             | <span data-ttu-id="1e4e8-137">Int32</span><span class="sxs-lookup"><span data-stu-id="1e4e8-137">Int32</span></span>         |                                        |
| <span data-ttu-id="1e4e8-138">`iULONG` (99)</span><span class="sxs-lookup"><span data-stu-id="1e4e8-138">`iULONG` (99)</span></span>            | <span data-ttu-id="1e4e8-139">UInt32</span><span class="sxs-lookup"><span data-stu-id="1e4e8-139">UInt32</span></span>        |                                        |
| <span data-ttu-id="1e4e8-140">`iBYTE` (100)</span><span class="sxs-lookup"><span data-stu-id="1e4e8-140">`iBYTE` (100)</span></span>            | <span data-ttu-id="1e4e8-141">Byte</span><span class="sxs-lookup"><span data-stu-id="1e4e8-141">Byte</span></span>          | <span data-ttu-id="1e4e8-142">El signo se extiende automáticamente a 32 bits.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-142">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="1e4e8-143">`iSTRING` (101)</span><span class="sxs-lookup"><span data-stu-id="1e4e8-143">`iSTRING` (101)</span></span>          | <span data-ttu-id="1e4e8-144">Índice de montón de cadena</span><span class="sxs-lookup"><span data-stu-id="1e4e8-144">String heap index</span></span> | <span data-ttu-id="1e4e8-145">*pval* es un índice del montón de cadenas.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-145">*pVal* is an index into the String heap.</span></span> <span data-ttu-id="1e4e8-146">Use [IMetadataTables:: GetString](imetadatatables-getstring-method.md) para obtener el valor de cadena de columna real.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-146">Use [IMetadataTables::GetString](imetadatatables-getstring-method.md) to get the actual column String value.</span></span> |
| <span data-ttu-id="1e4e8-147">`iGUID` (102)</span><span class="sxs-lookup"><span data-stu-id="1e4e8-147">`iGUID` (102)</span></span>            | <span data-ttu-id="1e4e8-148">Índice de montón GUID</span><span class="sxs-lookup"><span data-stu-id="1e4e8-148">Guid heap index</span></span> | <span data-ttu-id="1e4e8-149">*pval* es un índice en el montón de GUID.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-149">*pVal* is an index into the Guid heap.</span></span> <span data-ttu-id="1e4e8-150">Use [IMetadataTables:: GetGuid](imetadatatables-getguid-method.md) para obtener el valor de GUID de columna real.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-150">Use [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) to get the actual column Guid value.</span></span> |
| <span data-ttu-id="1e4e8-151">`iBLOB` (103)</span><span class="sxs-lookup"><span data-stu-id="1e4e8-151">`iBLOB` (103)</span></span>            | <span data-ttu-id="1e4e8-152">Índice de montón de BLOB</span><span class="sxs-lookup"><span data-stu-id="1e4e8-152">Blob heap index</span></span> | <span data-ttu-id="1e4e8-153">*pval* es un índice del montón de blobs.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-153">*pVal* is an index into the Blob heap.</span></span> <span data-ttu-id="1e4e8-154">Use [IMetadataTables:: GetBlob](imetadatatables-getblob-method.md) para obtener el valor de BLOB de columna real.</span><span class="sxs-lookup"><span data-stu-id="1e4e8-154">Use [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) to get the actual column Blob value.</span></span> |
  
## <a name="requirements"></a><span data-ttu-id="1e4e8-155">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1e4e8-155">Requirements</span></span>  

 <span data-ttu-id="1e4e8-156">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1e4e8-156">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1e4e8-157">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="1e4e8-157">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="1e4e8-158">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="1e4e8-158">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="1e4e8-159">**.NET Framework versiones**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1e4e8-159">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1e4e8-160">Vea también</span><span class="sxs-lookup"><span data-stu-id="1e4e8-160">See also</span></span>

- [<span data-ttu-id="1e4e8-161">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e4e8-161">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="1e4e8-162">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="1e4e8-162">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
