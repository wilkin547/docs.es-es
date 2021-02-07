---
description: 'Más información acerca de: IMetaDataTables:: GetColumnInfo (método)'
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
ms.openlocfilehash: 21980567c5f9b364362f7e3ff02ee3a5e60b01ee
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99688239"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="08895-103">IMetaDataTables::GetColumnInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="08895-103">IMetaDataTables::GetColumnInfo Method</span></span>

<span data-ttu-id="08895-104">Obtiene datos sobre la columna especificada de la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="08895-104">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="08895-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="08895-105">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="08895-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="08895-106">Parameters</span></span>

=======

 `ixTbl`  
 <span data-ttu-id="08895-107">de Índice de la tabla deseada.</span><span class="sxs-lookup"><span data-stu-id="08895-107">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="08895-108">de Índice de la columna deseada.</span><span class="sxs-lookup"><span data-stu-id="08895-108">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="08895-109">enuncia Puntero al desplazamiento de la columna de la fila.</span><span class="sxs-lookup"><span data-stu-id="08895-109">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="08895-110">enuncia Puntero al tamaño, en bytes, de la columna.</span><span class="sxs-lookup"><span data-stu-id="08895-110">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="08895-111">enuncia Puntero al tipo de los valores de la columna.</span><span class="sxs-lookup"><span data-stu-id="08895-111">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="08895-112">enuncia Un puntero a un puntero al nombre de la columna.</span><span class="sxs-lookup"><span data-stu-id="08895-112">[out] A pointer to a pointer to the column name.</span></span>  

## <a name="remarks"></a><span data-ttu-id="08895-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="08895-113">Remarks</span></span>

<span data-ttu-id="08895-114">El tipo de columna devuelto está dentro de un intervalo de valores:</span><span class="sxs-lookup"><span data-stu-id="08895-114">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="08895-115">pType</span><span class="sxs-lookup"><span data-stu-id="08895-115">pType</span></span>                    | <span data-ttu-id="08895-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="08895-116">Description</span></span>   | <span data-ttu-id="08895-117">Función auxiliar</span><span class="sxs-lookup"><span data-stu-id="08895-117">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="08895-118">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="08895-118">`0`..`iRidMax`</span></span><br><span data-ttu-id="08895-119">(0.. 63)</span><span class="sxs-lookup"><span data-stu-id="08895-119">(0..63)</span></span>   | <span data-ttu-id="08895-120">Libra</span><span class="sxs-lookup"><span data-stu-id="08895-120">Rid</span></span>           | <span data-ttu-id="08895-121">**IsRidType**</span><span class="sxs-lookup"><span data-stu-id="08895-121">**IsRidType**</span></span><br><span data-ttu-id="08895-122">**IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="08895-122">**IsRidOrToken**</span></span> |
| <span data-ttu-id="08895-123">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="08895-123">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="08895-124">(64.. 95)</span><span class="sxs-lookup"><span data-stu-id="08895-124">(64..95)</span></span> | <span data-ttu-id="08895-125">Token codificado</span><span class="sxs-lookup"><span data-stu-id="08895-125">Coded token</span></span> | <span data-ttu-id="08895-126">**IsCodedTokenType**</span><span class="sxs-lookup"><span data-stu-id="08895-126">**IsCodedTokenType**</span></span> <br><span data-ttu-id="08895-127">**IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="08895-127">**IsRidOrToken**</span></span> |
| <span data-ttu-id="08895-128">`iSHORT` (96)</span><span class="sxs-lookup"><span data-stu-id="08895-128">`iSHORT` (96)</span></span>            | <span data-ttu-id="08895-129">Int16</span><span class="sxs-lookup"><span data-stu-id="08895-129">Int16</span></span>         | <span data-ttu-id="08895-130">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="08895-130">**IsFixedType**</span></span>                   |
| <span data-ttu-id="08895-131">`iUSHORT` (97)</span><span class="sxs-lookup"><span data-stu-id="08895-131">`iUSHORT` (97)</span></span>           | <span data-ttu-id="08895-132">UInt16</span><span class="sxs-lookup"><span data-stu-id="08895-132">UInt16</span></span>        | <span data-ttu-id="08895-133">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="08895-133">**IsFixedType**</span></span>                   |
| <span data-ttu-id="08895-134">`iLONG` (98)</span><span class="sxs-lookup"><span data-stu-id="08895-134">`iLONG` (98)</span></span>             | <span data-ttu-id="08895-135">Int32</span><span class="sxs-lookup"><span data-stu-id="08895-135">Int32</span></span>         | <span data-ttu-id="08895-136">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="08895-136">**IsFixedType**</span></span>                   |
| <span data-ttu-id="08895-137">`iULONG` (99)</span><span class="sxs-lookup"><span data-stu-id="08895-137">`iULONG` (99)</span></span>            | <span data-ttu-id="08895-138">UInt32</span><span class="sxs-lookup"><span data-stu-id="08895-138">UInt32</span></span>        | <span data-ttu-id="08895-139">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="08895-139">**IsFixedType**</span></span>                   |
| <span data-ttu-id="08895-140">`iBYTE` (100)</span><span class="sxs-lookup"><span data-stu-id="08895-140">`iBYTE` (100)</span></span>            | <span data-ttu-id="08895-141">Byte</span><span class="sxs-lookup"><span data-stu-id="08895-141">Byte</span></span>          | <span data-ttu-id="08895-142">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="08895-142">**IsFixedType**</span></span>                   |
| <span data-ttu-id="08895-143">`iSTRING` (101)</span><span class="sxs-lookup"><span data-stu-id="08895-143">`iSTRING` (101)</span></span>          | <span data-ttu-id="08895-144">String</span><span class="sxs-lookup"><span data-stu-id="08895-144">String</span></span>        | <span data-ttu-id="08895-145">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="08895-145">**IsHeapType**</span></span>                    |
| <span data-ttu-id="08895-146">`iGUID` (102)</span><span class="sxs-lookup"><span data-stu-id="08895-146">`iGUID` (102)</span></span>            | <span data-ttu-id="08895-147">Guid</span><span class="sxs-lookup"><span data-stu-id="08895-147">Guid</span></span>          | <span data-ttu-id="08895-148">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="08895-148">**IsHeapType**</span></span>                    |
| <span data-ttu-id="08895-149">`iBLOB` (103)</span><span class="sxs-lookup"><span data-stu-id="08895-149">`iBLOB` (103)</span></span>            | <span data-ttu-id="08895-150">Blob</span><span class="sxs-lookup"><span data-stu-id="08895-150">Blob</span></span>          | <span data-ttu-id="08895-151">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="08895-151">**IsHeapType**</span></span>                    |

<span data-ttu-id="08895-152">Los valores que se almacenan en el *montón* (es decir, `IsHeapType == true` ) se pueden leer mediante:</span><span class="sxs-lookup"><span data-stu-id="08895-152">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="08895-153">`iSTRING`: **IMetadataTables. GetString**</span><span class="sxs-lookup"><span data-stu-id="08895-153">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="08895-154">`iGUID`: **IMetadataTables. GetGUID**</span><span class="sxs-lookup"><span data-stu-id="08895-154">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="08895-155">`iBLOB`: **IMetadataTables. GetBlob**</span><span class="sxs-lookup"><span data-stu-id="08895-155">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="08895-156">Para usar las constantes definidas en la tabla anterior, incluya la directiva `#define _DEFINE_META_DATA_META_CONSTANTS` proporcionada por el archivo de encabezado *Cor. h* .</span><span class="sxs-lookup"><span data-stu-id="08895-156">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="08895-157">Requisitos</span><span class="sxs-lookup"><span data-stu-id="08895-157">Requirements</span></span>  

 <span data-ttu-id="08895-158">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="08895-158">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="08895-159">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="08895-159">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="08895-160">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="08895-160">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="08895-161">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="08895-161">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="08895-162">Vea también</span><span class="sxs-lookup"><span data-stu-id="08895-162">See also</span></span>

- [<span data-ttu-id="08895-163">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="08895-163">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="08895-164">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="08895-164">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
