---
description: 'Más información acerca de: IMetaDataTables:: GetUserString ((método)'
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
ms.openlocfilehash: 0909bfb2dbf4e6a34b746da7397a82845c2129c2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99687693"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="7d9ab-103">IMetaDataTables::GetUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="7d9ab-103">IMetaDataTables::GetUserString Method</span></span>

<span data-ttu-id="7d9ab-104">Obtiene la cadena codificada de forma rígida en el índice especificado de la columna de cadena en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="7d9ab-104">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="7d9ab-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7d9ab-105">Syntax</span></span>

```cpp
HRESULT GetUserString (
    [in]  ULONG       ixUserString,
    [out] ULONG       *pcbData,
    [out] const void  **ppData
);
```

## <a name="parameters"></a><span data-ttu-id="7d9ab-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7d9ab-106">Parameters</span></span>

`ixUserString`\
<span data-ttu-id="7d9ab-107">de Valor de índice del que se recuperará la cadena codificada de forma rígida.</span><span class="sxs-lookup"><span data-stu-id="7d9ab-107">[in] The index value from which the hard-coded string will be retrieved.</span></span>

`pcbData`\
<span data-ttu-id="7d9ab-108">enuncia Puntero al tamaño de `ppData` .</span><span class="sxs-lookup"><span data-stu-id="7d9ab-108">[out] A pointer to the size of `ppData`.</span></span>

`ppData`\
<span data-ttu-id="7d9ab-109">enuncia Un puntero a un puntero a la cadena devuelta.</span><span class="sxs-lookup"><span data-stu-id="7d9ab-109">[out] A pointer to a pointer to the returned string.</span></span>

## <a name="requirements"></a><span data-ttu-id="7d9ab-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7d9ab-110">Requirements</span></span>

<span data-ttu-id="7d9ab-111">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7d9ab-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="7d9ab-112">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="7d9ab-112">**Header:** Cor.h</span></span>

<span data-ttu-id="7d9ab-113">**Biblioteca:** Se usa como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="7d9ab-113">**Library:** Used as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="7d9ab-114">**.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="7d9ab-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="7d9ab-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="7d9ab-115">See also</span></span>

- [<span data-ttu-id="7d9ab-116">IMetaDataTables (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d9ab-116">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="7d9ab-117">IMetaDataTables2 (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="7d9ab-117">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
