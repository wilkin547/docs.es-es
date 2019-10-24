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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: dd67d9faafedf4fb92c69618d4464ebb2ce47dcc
ms.sourcegitcommit: 559259da2738a7b33a46c0130e51d336091c2097
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/22/2019
ms.locfileid: "72774258"
---
# <a name="imetadatatablesgetcolumninfo-method"></a><span data-ttu-id="fb2f6-102">IMetaDataTables::GetColumnInfo (Método)</span><span class="sxs-lookup"><span data-stu-id="fb2f6-102">IMetaDataTables::GetColumnInfo Method</span></span>
<span data-ttu-id="fb2f6-103">Obtiene datos sobre la columna especificada de la tabla especificada.</span><span class="sxs-lookup"><span data-stu-id="fb2f6-103">Gets data about the specified column in the specified table.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fb2f6-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb2f6-104">Syntax</span></span>  
  
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
  
## <a name="parameters"></a><span data-ttu-id="fb2f6-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fb2f6-105">Parameters</span></span>
=======

 `ixTbl`  
 <span data-ttu-id="fb2f6-106">de Índice de la tabla deseada.</span><span class="sxs-lookup"><span data-stu-id="fb2f6-106">[in] The index of the desired table.</span></span>  
  
 `ixCol`  
 <span data-ttu-id="fb2f6-107">de Índice de la columna deseada.</span><span class="sxs-lookup"><span data-stu-id="fb2f6-107">[in] The index of the desired column.</span></span>  
  
 `poCol`  
 <span data-ttu-id="fb2f6-108">enuncia Puntero al desplazamiento de la columna de la fila.</span><span class="sxs-lookup"><span data-stu-id="fb2f6-108">[out] A pointer to the offset of the column in the row.</span></span>  
  
 `pcbCol`  
 <span data-ttu-id="fb2f6-109">enuncia Puntero al tamaño, en bytes, de la columna.</span><span class="sxs-lookup"><span data-stu-id="fb2f6-109">[out] A pointer to the size, in bytes, of the column.</span></span>  
  
 `pType`  
 <span data-ttu-id="fb2f6-110">enuncia Puntero al tipo de los valores de la columna.</span><span class="sxs-lookup"><span data-stu-id="fb2f6-110">[out] A pointer to the type of the values in the column.</span></span>  
  
 `ppName`  
 <span data-ttu-id="fb2f6-111">enuncia Un puntero a un puntero al nombre de la columna.</span><span class="sxs-lookup"><span data-stu-id="fb2f6-111">[out] A pointer to a pointer to the column name.</span></span>  
 
## <a name="remarks"></a><span data-ttu-id="fb2f6-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fb2f6-112">Remarks</span></span>

<span data-ttu-id="fb2f6-113">El tipo de columna devuelto está dentro de un intervalo de valores:</span><span class="sxs-lookup"><span data-stu-id="fb2f6-113">The returned column type falls within a range of values:</span></span>

| <span data-ttu-id="fb2f6-114">pType</span><span class="sxs-lookup"><span data-stu-id="fb2f6-114">pType</span></span>                    | <span data-ttu-id="fb2f6-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb2f6-115">Description</span></span>   | <span data-ttu-id="fb2f6-116">Función auxiliar</span><span class="sxs-lookup"><span data-stu-id="fb2f6-116">Helper function</span></span>                   |
|--------------------------|---------------|-----------------------------------|
| <span data-ttu-id="fb2f6-117">`0`..`iRidMax`</span><span class="sxs-lookup"><span data-stu-id="fb2f6-117">`0`..`iRidMax`</span></span><br><span data-ttu-id="fb2f6-118">(0.. 63)</span><span class="sxs-lookup"><span data-stu-id="fb2f6-118">(0..63)</span></span>   | <span data-ttu-id="fb2f6-119">Libra</span><span class="sxs-lookup"><span data-stu-id="fb2f6-119">Rid</span></span>           | <span data-ttu-id="fb2f6-120">**IsRidType**</span><span class="sxs-lookup"><span data-stu-id="fb2f6-120">**IsRidType**</span></span><br><span data-ttu-id="fb2f6-121">**IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="fb2f6-121">**IsRidOrToken**</span></span> |
| <span data-ttu-id="fb2f6-122">`iCodedToken`..`iCodedTokenMax`</span><span class="sxs-lookup"><span data-stu-id="fb2f6-122">`iCodedToken`..`iCodedTokenMax`</span></span><br><span data-ttu-id="fb2f6-123">(64.. 95)</span><span class="sxs-lookup"><span data-stu-id="fb2f6-123">(64..95)</span></span> | <span data-ttu-id="fb2f6-124">Token codificado</span><span class="sxs-lookup"><span data-stu-id="fb2f6-124">Coded token</span></span> | <span data-ttu-id="fb2f6-125">**IsCodedTokenType**</span><span class="sxs-lookup"><span data-stu-id="fb2f6-125">**IsCodedTokenType**</span></span> <br><span data-ttu-id="fb2f6-126">**IsRidOrToken**</span><span class="sxs-lookup"><span data-stu-id="fb2f6-126">**IsRidOrToken**</span></span> |
| <span data-ttu-id="fb2f6-127">`iSHORT` (96)</span><span class="sxs-lookup"><span data-stu-id="fb2f6-127">`iSHORT` (96)</span></span>            | <span data-ttu-id="fb2f6-128">Int16</span><span class="sxs-lookup"><span data-stu-id="fb2f6-128">Int16</span></span>         | <span data-ttu-id="fb2f6-129">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="fb2f6-129">**IsFixedType**</span></span>                   |
| <span data-ttu-id="fb2f6-130">`iUSHORT` (97)</span><span class="sxs-lookup"><span data-stu-id="fb2f6-130">`iUSHORT` (97)</span></span>           | <span data-ttu-id="fb2f6-131">UInt16</span><span class="sxs-lookup"><span data-stu-id="fb2f6-131">UInt16</span></span>        | <span data-ttu-id="fb2f6-132">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="fb2f6-132">**IsFixedType**</span></span>                   |
| <span data-ttu-id="fb2f6-133">`iLONG` (98)</span><span class="sxs-lookup"><span data-stu-id="fb2f6-133">`iLONG` (98)</span></span>             | <span data-ttu-id="fb2f6-134">Int32</span><span class="sxs-lookup"><span data-stu-id="fb2f6-134">Int32</span></span>         | <span data-ttu-id="fb2f6-135">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="fb2f6-135">**IsFixedType**</span></span>                   |
| <span data-ttu-id="fb2f6-136">`iULONG` (99)</span><span class="sxs-lookup"><span data-stu-id="fb2f6-136">`iULONG` (99)</span></span>            | <span data-ttu-id="fb2f6-137">UInt32</span><span class="sxs-lookup"><span data-stu-id="fb2f6-137">UInt32</span></span>        | <span data-ttu-id="fb2f6-138">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="fb2f6-138">**IsFixedType**</span></span>                   |
| <span data-ttu-id="fb2f6-139">`iBYTE` (100)</span><span class="sxs-lookup"><span data-stu-id="fb2f6-139">`iBYTE` (100)</span></span>            | <span data-ttu-id="fb2f6-140">Byte</span><span class="sxs-lookup"><span data-stu-id="fb2f6-140">Byte</span></span>          | <span data-ttu-id="fb2f6-141">**IsFixedType**</span><span class="sxs-lookup"><span data-stu-id="fb2f6-141">**IsFixedType**</span></span>                   |
| <span data-ttu-id="fb2f6-142">`iSTRING` (101)</span><span class="sxs-lookup"><span data-stu-id="fb2f6-142">`iSTRING` (101)</span></span>          | <span data-ttu-id="fb2f6-143">String</span><span class="sxs-lookup"><span data-stu-id="fb2f6-143">String</span></span>        | <span data-ttu-id="fb2f6-144">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="fb2f6-144">**IsHeapType**</span></span>                    |
| <span data-ttu-id="fb2f6-145">`iGUID` (102)</span><span class="sxs-lookup"><span data-stu-id="fb2f6-145">`iGUID` (102)</span></span>            | <span data-ttu-id="fb2f6-146">GUID</span><span class="sxs-lookup"><span data-stu-id="fb2f6-146">Guid</span></span>          | <span data-ttu-id="fb2f6-147">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="fb2f6-147">**IsHeapType**</span></span>                    |
| <span data-ttu-id="fb2f6-148">`iBLOB` (103)</span><span class="sxs-lookup"><span data-stu-id="fb2f6-148">`iBLOB` (103)</span></span>            | <span data-ttu-id="fb2f6-149">Blob</span><span class="sxs-lookup"><span data-stu-id="fb2f6-149">Blob</span></span>          | <span data-ttu-id="fb2f6-150">**IsHeapType**</span><span class="sxs-lookup"><span data-stu-id="fb2f6-150">**IsHeapType**</span></span>                    |

<span data-ttu-id="fb2f6-151">Los valores que se almacenan en el *montón* (es decir, `IsHeapType == true`) se pueden leer mediante:</span><span class="sxs-lookup"><span data-stu-id="fb2f6-151">Values that are stored in the *heap* (that is, `IsHeapType == true`) can be read using:</span></span>

- <span data-ttu-id="fb2f6-152">`iSTRING`: **IMetadataTables. GetString**</span><span class="sxs-lookup"><span data-stu-id="fb2f6-152">`iSTRING`: **IMetadataTables.GetString**</span></span>
- <span data-ttu-id="fb2f6-153">`iGUID`: **IMetadataTables. GetGUID**</span><span class="sxs-lookup"><span data-stu-id="fb2f6-153">`iGUID`: **IMetadataTables.GetGUID**</span></span>
- <span data-ttu-id="fb2f6-154">`iBLOB`: **IMetadataTables. GetBlob**</span><span class="sxs-lookup"><span data-stu-id="fb2f6-154">`iBLOB`: **IMetadataTables.GetBlob**</span></span>

> [!IMPORTANT]
> <span data-ttu-id="fb2f6-155">Para usar las constantes definidas en la tabla anterior, incluya la Directiva `#define _DEFINE_META_DATA_META_CONSTANTS` proporciona el archivo de encabezado *Cor. h* .</span><span class="sxs-lookup"><span data-stu-id="fb2f6-155">To use the constants defined in the table above, include the directive `#define _DEFINE_META_DATA_META_CONSTANTS` provided by the *cor.h* header file.</span></span>

## <a name="requirements"></a><span data-ttu-id="fb2f6-156">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb2f6-156">Requirements</span></span>  
 <span data-ttu-id="fb2f6-157">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb2f6-157">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb2f6-158">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="fb2f6-158">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fb2f6-159">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="fb2f6-159">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="fb2f6-160">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fb2f6-160">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb2f6-161">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb2f6-161">See also</span></span>

- [<span data-ttu-id="fb2f6-162">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fb2f6-162">IMetaDataTables Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables-interface.md)
- [<span data-ttu-id="fb2f6-163">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="fb2f6-163">IMetaDataTables2 Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatatables2-interface.md)
