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
ms.openlocfilehash: 5936ca837c9ab452e992fcb09aacb476ab37316a
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74431437"
---
# <a name="imetadatatablesgetuserstring-method"></a><span data-ttu-id="b6c7b-102">IMetaDataTables::GetUserString (Método)</span><span class="sxs-lookup"><span data-stu-id="b6c7b-102">IMetaDataTables::GetUserString Method</span></span>

<span data-ttu-id="b6c7b-103">Obtiene la cadena codificada de forma rígida en el índice especificado de la columna de cadena en el ámbito actual.</span><span class="sxs-lookup"><span data-stu-id="b6c7b-103">Gets the hard-coded string at the specified index in the string column in the current scope.</span></span>

## <a name="syntax"></a><span data-ttu-id="b6c7b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b6c7b-104">Syntax</span></span>

```cpp
HRESULT GetUserString (
    [in]  ULONG       ixUserString,
    [out] ULONG       *pcbData,
    [out] const void  **ppData
);
```

## <a name="parameters"></a><span data-ttu-id="b6c7b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b6c7b-105">Parameters</span></span>

`ixUserString`\
<span data-ttu-id="b6c7b-106">de Valor de índice del que se recuperará la cadena codificada de forma rígida.</span><span class="sxs-lookup"><span data-stu-id="b6c7b-106">[in] The index value from which the hard-coded string will be retrieved.</span></span>

`pcbData`\
<span data-ttu-id="b6c7b-107">enuncia Puntero al tamaño de `ppData`.</span><span class="sxs-lookup"><span data-stu-id="b6c7b-107">[out] A pointer to the size of `ppData`.</span></span>

`ppData`\
<span data-ttu-id="b6c7b-108">enuncia Un puntero a un puntero a la cadena devuelta.</span><span class="sxs-lookup"><span data-stu-id="b6c7b-108">[out] A pointer to a pointer to the returned string.</span></span>

## <a name="requirements"></a><span data-ttu-id="b6c7b-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b6c7b-109">Requirements</span></span>

<span data-ttu-id="b6c7b-110">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b6c7b-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="b6c7b-111">**Encabezado:** Cor. h</span><span class="sxs-lookup"><span data-stu-id="b6c7b-111">**Header:** Cor.h</span></span>

<span data-ttu-id="b6c7b-112">**Biblioteca:** Se utiliza como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="b6c7b-112">**Library:** Used as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="b6c7b-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b6c7b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b6c7b-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="b6c7b-114">See also</span></span>

- [<span data-ttu-id="b6c7b-115">IMetaDataTables (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6c7b-115">IMetaDataTables Interface</span></span>](imetadatatables-interface.md)
- [<span data-ttu-id="b6c7b-116">IMetaDataTables2 (interfaz)</span><span class="sxs-lookup"><span data-stu-id="b6c7b-116">IMetaDataTables2 Interface</span></span>](imetadatatables2-interface.md)
