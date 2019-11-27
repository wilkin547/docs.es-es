---
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
ms.openlocfilehash: 376b9ff09ad38ca43d57fcf064458e0331da8aad
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74441997"
---
# <a name="imetadatatablesgetcolumn-method"></a><span data-ttu-id="6b7b1-102">IMetaDataTables::GetColumn (Método)</span><span class="sxs-lookup"><span data-stu-id="6b7b1-102">IMetaDataTables::GetColumn Method</span></span>
<span data-ttu-id="6b7b1-103">Obtiene un puntero al valor contenido en la celda de la columna y la fila especificadas en la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-103">Gets a pointer to the value contained in the cell of the specified column and row in the given table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6b7b1-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="6b7b1-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumn (   
    [in]  ULONG   ixTbl,  
    [in]  ULONG   ixCol,  
    [in]  ULONG   rid,  
    [out] ULONG   *pVal  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6b7b1-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="6b7b1-105">Parameters</span></span>

 `ixTbl`  
 <span data-ttu-id="6b7b1-106">de Índice de la tabla.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-106">[in] The index of the table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="6b7b1-107">de Índice de la columna de la tabla.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-107">[in] The index of the column in the table.</span></span>  
  
 `rid`  
 <span data-ttu-id="6b7b1-108">de Índice de la fila de la tabla.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-108">[in] The index of the row in the table.</span></span>  
  
 `pVal`  
 <span data-ttu-id="6b7b1-109">enuncia Puntero al valor de la celda.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-109">[out] A pointer to the value in the cell.</span></span>  
 
## <a name="remarks"></a><span data-ttu-id="6b7b1-110">Comentarios</span><span class="sxs-lookup"><span data-stu-id="6b7b1-110">Remarks</span></span>

<span data-ttu-id="6b7b1-111">La interpretación del valor devuelto a través de `pVal` depende del tipo de la columna.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-111">The interpretion of the value returned through `pVal` depends on the column's type.</span></span> <span data-ttu-id="6b7b1-112">El tipo de columna se puede determinar mediante una llamada a [IMetaDataTables. GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span><span class="sxs-lookup"><span data-stu-id="6b7b1-112">The column type can be determined by calling [IMetaDataTables.GetColumnInfo](imetadatatables-getcolumninfo-method.md).</span></span>

- <span data-ttu-id="6b7b1-113">El método **getcolumn (** convierte automáticamente las columnas de tipo **RID** o **CodedToken** en valores `mdToken` de 32 bits completos.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-113">The **GetColumn** method automatically converts columns of type **Rid** or **CodedToken** to full 32-bit `mdToken` values.</span></span>
- <span data-ttu-id="6b7b1-114">También convierte automáticamente los valores de 8 o 16 bits en valores completos de 32 bits.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-114">It also automatically converts 8-bit or 16-bit values to full 32-bit values.</span></span> 
- <span data-ttu-id="6b7b1-115">En el caso de las columnas de tipo de *montón* , el *pval* devuelto será un índice en el montón correspondiente.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-115">For *heap* type columns, the returned *pVal* will be an index into the corresponding heap.</span></span>

| <span data-ttu-id="6b7b1-116">Tipo de columna</span><span class="sxs-lookup"><span data-stu-id="6b7b1-116">Column type</span></span>              | <span data-ttu-id="6b7b1-117">pVal contiene</span><span class="sxs-lookup"><span data-stu-id="6b7b1-117">pVal contains</span></span> | <span data-ttu-id="6b7b1-118">Comentario</span><span class="sxs-lookup"><span data-stu-id="6b7b1-118">Comment</span></span>                          |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="6b7b1-119">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="6b7b1-119">`0`..`iRidMax`</span></span><br><span data-ttu-id="6b7b1-120">(0.. 63)</span><span class="sxs-lookup"><span data-stu-id="6b7b1-120">(0..63)</span></span>  | <span data-ttu-id="6b7b1-121">mdToken</span><span class="sxs-lookup"><span data-stu-id="6b7b1-121">mdToken</span></span>     | <span data-ttu-id="6b7b1-122">*pval* contendrá un token completo.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-122">*pVal* will contain a full Token.</span></span> <span data-ttu-id="6b7b1-123">La función convierte automáticamente el RID en un token completo.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-123">The function automatically converts the Rid into a full token.</span></span> |
| <span data-ttu-id="6b7b1-124">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="6b7b1-124">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="6b7b1-125">(64.. 95)</span><span class="sxs-lookup"><span data-stu-id="6b7b1-125">(64..95)</span></span> | <span data-ttu-id="6b7b1-126">mdToken</span><span class="sxs-lookup"><span data-stu-id="6b7b1-126">mdToken</span></span> | <span data-ttu-id="6b7b1-127">Después de la devolución, *pval* contendrá un token completo.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-127">Upon return, *pVal* will contain a full Token.</span></span> <span data-ttu-id="6b7b1-128">La función descomprime automáticamente CodedToken en un token completo.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-128">The function automatically decompresses the CodedToken into a full token.</span></span> |
| <span data-ttu-id="6b7b1-129">`iSHORT` (96)</span><span class="sxs-lookup"><span data-stu-id="6b7b1-129">`iSHORT` (96)</span></span>            | <span data-ttu-id="6b7b1-130">Int16</span><span class="sxs-lookup"><span data-stu-id="6b7b1-130">Int16</span></span>         | <span data-ttu-id="6b7b1-131">El signo se extiende automáticamente a 32 bits.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-131">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="6b7b1-132">`iUSHORT` (97)</span><span class="sxs-lookup"><span data-stu-id="6b7b1-132">`iUSHORT` (97)</span></span>           | <span data-ttu-id="6b7b1-133">UInt16</span><span class="sxs-lookup"><span data-stu-id="6b7b1-133">UInt16</span></span>        | <span data-ttu-id="6b7b1-134">El signo se extiende automáticamente a 32 bits.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-134">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="6b7b1-135">`iLONG` (98)</span><span class="sxs-lookup"><span data-stu-id="6b7b1-135">`iLONG` (98)</span></span>             | <span data-ttu-id="6b7b1-136">Int32</span><span class="sxs-lookup"><span data-stu-id="6b7b1-136">Int32</span></span>         |                                        | 
| <span data-ttu-id="6b7b1-137">`iULONG` (99)</span><span class="sxs-lookup"><span data-stu-id="6b7b1-137">`iULONG` (99)</span></span>            | <span data-ttu-id="6b7b1-138">UInt32</span><span class="sxs-lookup"><span data-stu-id="6b7b1-138">UInt32</span></span>        |                                        |
| <span data-ttu-id="6b7b1-139">`iBYTE` (100)</span><span class="sxs-lookup"><span data-stu-id="6b7b1-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="6b7b1-140">Byte</span><span class="sxs-lookup"><span data-stu-id="6b7b1-140">Byte</span></span>          | <span data-ttu-id="6b7b1-141">El signo se extiende automáticamente a 32 bits.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-141">Automatically sign-extended to 32-bit.</span></span>  |
| <span data-ttu-id="6b7b1-142">`iSTRING` (101)</span><span class="sxs-lookup"><span data-stu-id="6b7b1-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="6b7b1-143">Índice de montón de cadena</span><span class="sxs-lookup"><span data-stu-id="6b7b1-143">String heap index</span></span> | <span data-ttu-id="6b7b1-144">*pval* es un índice del montón de cadenas.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-144">*pVal* is an index into the String heap.</span></span> <span data-ttu-id="6b7b1-145">Use [IMetadataTables:: GetString](imetadatatables-getstring-method.md) para obtener el valor de cadena de columna real.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-145">Use [IMetadataTables::GetString](imetadatatables-getstring-method.md) to get the actual column String value.</span></span> |
| <span data-ttu-id="6b7b1-146">`iGUID` (102)</span><span class="sxs-lookup"><span data-stu-id="6b7b1-146">`iGUID` (102)</span></span>            | <span data-ttu-id="6b7b1-147">Índice de montón GUID</span><span class="sxs-lookup"><span data-stu-id="6b7b1-147">Guid heap index</span></span> | <span data-ttu-id="6b7b1-148">*pval* es un índice en el montón de GUID.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-148">*pVal* is an index into the Guid heap.</span></span> <span data-ttu-id="6b7b1-149">Use [IMetadataTables:: GetGuid](imetadatatables-getguid-method.md) para obtener el valor de GUID de columna real.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-149">Use [IMetadataTables::GetGuid](imetadatatables-getguid-method.md) to get the actual column Guid value.</span></span> |
| <span data-ttu-id="6b7b1-150">`iBLOB` (103)</span><span class="sxs-lookup"><span data-stu-id="6b7b1-150">`iBLOB` (103)</span></span>            | <span data-ttu-id="6b7b1-151">Índice de montón de BLOB</span><span class="sxs-lookup"><span data-stu-id="6b7b1-151">Blob heap index</span></span> | <span data-ttu-id="6b7b1-152">*pval* es un índice del montón de blobs.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-152">*pVal* is an index into the Blob heap.</span></span> <span data-ttu-id="6b7b1-153">Use [IMetadataTables:: GetBlob](imetadatatables-getblob-method.md) para obtener el valor de BLOB de columna real.</span><span class="sxs-lookup"><span data-stu-id="6b7b1-153">Use [IMetadataTables::GetBlob](imetadatatables-getblob-method.md) to get the actual column Blob value.</span></span> |
  
## <a name="requirements"></a><span data-ttu-id="6b7b1-154">Requisitos</span><span class="sxs-lookup"><span data-stu-id="6b7b1-154">Requirements</span></span>  
 <span data-ttu-id="6b7b1-155">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="6b7b1-155">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6b7b1-156">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="6b7b1-156">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6b7b1-157">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="6b7b1-157">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6b7b1-158">**.NET Framework versiones** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6b7b1-158">**.NET Framework Versions** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6b7b1-159">Vea también</span><span class="sxs-lookup"><span data-stu-id="6b7b1-159">See also</span></span>

- [<span data-ttu-id="6b7b1-160">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6b7b1-160">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="6b7b1-161">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="6b7b1-161">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
