---
title: IMetaDataTables::GetUserString (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataTables.GetUserString
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataTables::GetUserString
helpviewer_keywords:
- IMetaDataTables::GetUserString method [.NET Framework metadata]
- GetUserString method, IMetaDataTables interface [.NET Framework metadata]
ms.assetid: 35b8f0d6-9aba-4714-adb2-62020a38fb7e
topic_type:
- apiref
ms.openlocfilehash: 21ce66722e069573b651ada950b64ef6d97220fb
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84501149"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="07b5e-102">IMetaDataTables::GetUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="07b5e-102">IMetaDataTables::GetUserString Method</span></span>

<span data-ttu-id="07b5e-103">Obtiene la cadena codificada de forma rígida en el índice especificado de la columna de cadena en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="07b5e-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="07b5e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07b5e-104">Syntax</span></span>

```cpp
HRESULT GetUserString (
    [in]  ULONG       ixUserString,
    [out] ULONG       *pcbData,
    [out] const void  **ppData
);
```

## <a name="parameters"></a><span data-ttu-id="07b5e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="07b5e-105">Parameters</span></span>

`ixUserString`\
<span data-ttu-id="07b5e-106">de Valor de índice del que se recuperará la cadena codificada de forma rígida.</span><span class="sxs-lookup"><span data-stu-id="07b5e-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>

`pcbData`\
<span data-ttu-id="07b5e-107">enuncia Puntero al tamaño de `ppData` .</span><span class="sxs-lookup"><span data-stu-id="07b5e-107">[out] A pointer to the size of `ppData`.</span></span>

`ppData`\
<span data-ttu-id="07b5e-108">enuncia Un puntero a un puntero a la cadena devuelta.</span><span class="sxs-lookup"><span data-stu-id="07b5e-108">[out] A pointer to a pointer to the returned string.</span></span>

## <a name="requirements"></a><span data-ttu-id="07b5e-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="07b5e-109">Requirements</span></span>

<span data-ttu-id="07b5e-110">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07b5e-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="07b5e-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="07b5e-111">**Header:** Cor.h</span></span>

<span data-ttu-id="07b5e-112">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="07b5e-112">**Library:** Used as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="07b5e-113">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="07b5e-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="07b5e-114">Consulte también:</span><span class="sxs-lookup"><span data-stu-id="07b5e-114">See also</span></span>

- [<span data-ttu-id="07b5e-115">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="07b5e-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="07b5e-116">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="07b5e-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
