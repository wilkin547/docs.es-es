---
title: IMetaDataTables::GetColumnInfo (Método)
ms.date: 10/10/2019
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
ms.openlocfilehash: cc8aac32149fed952737d928e16a8f6efc448c79
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177120"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="285ef-102">IMetaDataTables::GetColumnInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="285ef-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="285ef-103">Obtiene datos sobre la columna especificada en la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="285ef-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="285ef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="285ef-104">Syntax</span></span>  
  
```cpp  
HRESULT GetColumnInfo (
    [in]  ULONG        ixTbl,  
    [in]  ULONG        ixCol,  
    [out] ULONG        *poCol,  
    [out] ULONG        *pcbCol,  
    [out] ULONG        *pType,  
    [out] const char   **ppName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="285ef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="285ef-105">Parameters</span></span>
=======

 `ixTbl`  
 <span data-ttu-id="285ef-106">[en] El índice de la tabla deseada.</span><span class="sxs-lookup"><span data-stu-id="285ef-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="285ef-107">[en] El índice de la columna deseada.</span><span class="sxs-lookup"><span data-stu-id="285ef-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="285ef-108">[fuera] Un puntero al desplazamiento de la columna de la fila.</span><span class="sxs-lookup"><span data-stu-id="285ef-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="285ef-109">[fuera] Un puntero al tamaño, en bytes, de la columna.</span><span class="sxs-lookup"><span data-stu-id="285ef-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="285ef-110">[fuera] Un puntero al tipo de los valores de la columna.</span><span class="sxs-lookup"><span data-stu-id="285ef-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="285ef-111">[fuera] Puntero a un puntero al nombre de la columna.</span><span class="sxs-lookup"><span data-stu-id="285ef-111">[out] A pointer to a pointer to the column name.</span></span>  

## <a name="remarks"></a><span data-ttu-id="285ef-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="285ef-112">Remarks</span></span>

<span data-ttu-id="285ef-113">El tipo de columna devuelto se encuentra dentro de un intervalo de valores:</span><span class="sxs-lookup"><span data-stu-id="285ef-113">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="285ef-114">pType</span><span class="sxs-lookup"><span data-stu-id="285ef-114">pType</span></span>                    | <span data-ttu-id="285ef-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="285ef-115">Description</span></span>   | <span data-ttu-id="285ef-116">Función auxiliar</span><span class="sxs-lookup"><span data-stu-id="285ef-116">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="285ef-117">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="285ef-117">`0`..`iRidMax`</span></span><br><span data-ttu-id="285ef-118">(0..63)</span><span class="sxs-lookup"><span data-stu-id="285ef-118">(0..63)</span></span>   | <span data-ttu-id="285ef-119">Librar</span><span class="sxs-lookup"><span data-stu-id="285ef-119">Rid</span></span>           | <span data-ttu-id="285ef-120">**IsRidType**</span><span class="sxs-lookup"><span data-stu-id="285ef-120">**IsRidType**</span></span><br><span data-ttu-id="285ef-121">**IsridOrToken**</span><span class="sxs-lookup"><span data-stu-id="285ef-121">**IsRidOrToken**</span></span> |
| <span data-ttu-id="285ef-122">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="285ef-122">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="285ef-123">(64..95)</span><span class="sxs-lookup"><span data-stu-id="285ef-123">(64..95)</span></span> | <span data-ttu-id="285ef-124">Token codificado</span><span class="sxs-lookup"><span data-stu-id="285ef-124">Coded token</span></span> | <span data-ttu-id="285ef-125">**IsCodedTokenType**</span><span class="sxs-lookup"><span data-stu-id="285ef-125">**IsCodedTokenType**</span></span> <br><span data-ttu-id="285ef-126">**IsridOrToken**</span><span class="sxs-lookup"><span data-stu-id="285ef-126">**IsRidOrToken**</span></span> |
| <span data-ttu-id="285ef-127">`iSHORT`(96)</span><span class="sxs-lookup"><span data-stu-id="285ef-127">`iSHORT` (96)</span></span>            | <span data-ttu-id="285ef-128">Int16</span><span class="sxs-lookup"><span data-stu-id="285ef-128">Int16</span></span>         | <span data-ttu-id="285ef-129">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="285ef-129">**IsFixedType**</span></span>                   |
| <span data-ttu-id="285ef-130">`iUSHORT`(97)</span><span class="sxs-lookup"><span data-stu-id="285ef-130">`iUSHORT` (97)</span></span>           | <span data-ttu-id="285ef-131">UInt16</span><span class="sxs-lookup"><span data-stu-id="285ef-131">UInt16</span></span>        | <span data-ttu-id="285ef-132">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="285ef-132">**IsFixedType**</span></span>                   |
| <span data-ttu-id="285ef-133">`iLONG`(98)</span><span class="sxs-lookup"><span data-stu-id="285ef-133">`iLONG` (98)</span></span>             | <span data-ttu-id="285ef-134">Int32</span><span class="sxs-lookup"><span data-stu-id="285ef-134">Int32</span></span>         | <span data-ttu-id="285ef-135">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="285ef-135">**IsFixedType**</span></span>                   |
| <span data-ttu-id="285ef-136">`iULONG`(99)</span><span class="sxs-lookup"><span data-stu-id="285ef-136">`iULONG` (99)</span></span>            | <span data-ttu-id="285ef-137">UInt32</span><span class="sxs-lookup"><span data-stu-id="285ef-137">UInt32</span></span>        | <span data-ttu-id="285ef-138">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="285ef-138">**IsFixedType**</span></span>                   |
| <span data-ttu-id="285ef-139">`iBYTE`(100)</span><span class="sxs-lookup"><span data-stu-id="285ef-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="285ef-140">Byte</span><span class="sxs-lookup"><span data-stu-id="285ef-140">Byte</span></span>          | <span data-ttu-id="285ef-141">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="285ef-141">**IsFixedType**</span></span>                   |
| <span data-ttu-id="285ef-142">`iSTRING`(101)</span><span class="sxs-lookup"><span data-stu-id="285ef-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="285ef-143">String</span><span class="sxs-lookup"><span data-stu-id="285ef-143">String</span></span>        | <span data-ttu-id="285ef-144">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="285ef-144">**IsHeapType**</span></span>                    |
| <span data-ttu-id="285ef-145">`iGUID`(102)</span><span class="sxs-lookup"><span data-stu-id="285ef-145">`iGUID` (102)</span></span>            | <span data-ttu-id="285ef-146">Guid</span><span class="sxs-lookup"><span data-stu-id="285ef-146">Guid</span></span>          | <span data-ttu-id="285ef-147">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="285ef-147">**IsHeapType**</span></span>                    |
| <span data-ttu-id="285ef-148">`iBLOB`(103)</span><span class="sxs-lookup"><span data-stu-id="285ef-148">`iBLOB` (103)</span></span>            | <span data-ttu-id="285ef-149">Blob</span><span class="sxs-lookup"><span data-stu-id="285ef-149">Blob</span></span>          | <span data-ttu-id="285ef-150">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="285ef-150">**IsHeapType**</span></span>                    |

<span data-ttu-id="285ef-151">Los valores que se almacenan en `IsHeapType == true`el *montón* (es decir, ) se pueden leer mediante:</span><span class="sxs-lookup"><span data-stu-id="285ef-151">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="285ef-152">`iSTRING`: **IMetadataTables.GetString**</span><span class="sxs-lookup"><span data-stu-id="285ef-152">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="285ef-153">`iGUID`: **IMetadataTables.GetGUID**</span><span class="sxs-lookup"><span data-stu-id="285ef-153">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="285ef-154">`iBLOB`: **IMetadataTables.GetBlob**</span><span class="sxs-lookup"><span data-stu-id="285ef-154">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="285ef-155">Para utilizar las constantes definidas en la `#define _DEFINE_META_DATA_META_CONSTANTS` tabla anterior, incluya la directiva proporcionada por el archivo de encabezado *cor.h.*</span><span class="sxs-lookup"><span data-stu-id="285ef-155">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="285ef-156">Requisitos</span><span class="sxs-lookup"><span data-stu-id="285ef-156">Requirements</span></span>  
 <span data-ttu-id="285ef-157">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="285ef-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="285ef-158">**Encabezado:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="285ef-158">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="285ef-159">**Biblioteca:** Se utiliza como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="285ef-159">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="285ef-160">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="285ef-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="285ef-161">Consulte también</span><span class="sxs-lookup"><span data-stu-id="285ef-161">See also</span></span>

- [<span data-ttu-id="285ef-162">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="285ef-162">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="285ef-163">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="285ef-163">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
