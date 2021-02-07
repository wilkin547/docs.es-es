---
description: 'Más información acerca de: GetHashFromBlob ((función)'
title: GetHashFromBlob (Función)
ms.date: 03/30/2017
api_name:
- GetHashFromBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- GetHashFromBlob
helpviewer_keywords:
- GetHashFromBlob function [.NET Framework strong naming]
ms.assetid: b712d862-f2d0-4b55-87d4-65bbeadef982
topic_type:
- apiref
ms.openlocfilehash: dc5039e44440afa7a000bc61167faec0e5b6cc84
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736614"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="aceb6-103">GetHashFromBlob (Función)</span><span class="sxs-lookup"><span data-stu-id="aceb6-103">GetHashFromBlob Function</span></span>

<span data-ttu-id="aceb6-104">Obtiene un hash del ensamblado en la dirección de memoria especificada mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="aceb6-104">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>

<span data-ttu-id="aceb6-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="aceb6-105">This function has been deprecated.</span></span> <span data-ttu-id="aceb6-106">Use el método [ICLRStrongName:: GetHashFromBlob (](../hosting/iclrstrongname-gethashfromblob-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="aceb6-106">Use the [ICLRStrongName::GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="aceb6-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="aceb6-107">Syntax</span></span>

```cpp
HRESULT GetHashFromBlob (
    [in]  BYTE    *pbBlob,
    [in]  DWORD   cchBlob,
    [in, out] unsigned int   *piHashAlg,
    [out] BYTE    *pbHash,
    [in]  DWORD   cchHash,
    [out] DWORD   *pchHash
);
```

## <a name="parameters"></a><span data-ttu-id="aceb6-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="aceb6-108">Parameters</span></span>

`pbBlob`\
<span data-ttu-id="aceb6-109">de Puntero a la dirección del bloque de memoria al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="aceb6-109">[in] A pointer to the address of the memory block to be hashed.</span></span>

`cchBlob`\
<span data-ttu-id="aceb6-110">de La longitud, en bytes, del bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="aceb6-110">[in] The length, in bytes, of the memory block.</span></span>

`piHashAlg`\
<span data-ttu-id="aceb6-111">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="aceb6-111">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="aceb6-112">Use cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="aceb6-112">Use zero for the default algorithm.</span></span>

`pbHash`\
<span data-ttu-id="aceb6-113">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="aceb6-113">[out] The returned hash buffer.</span></span>

`cchHash`\
<span data-ttu-id="aceb6-114">de Tamaño máximo solicitado de `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="aceb6-114">[in] The requested maximum size of `pbHash`.</span></span>

`pchHash`\
<span data-ttu-id="aceb6-115">enuncia Tamaño, en bytes, del devuelto `pbHash` .</span><span class="sxs-lookup"><span data-stu-id="aceb6-115">[out] The size, in bytes, of the returned `pbHash`.</span></span>

## <a name="requirements"></a><span data-ttu-id="aceb6-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="aceb6-116">Requirements</span></span>

<span data-ttu-id="aceb6-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="aceb6-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="aceb6-118">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="aceb6-118">**Header:** StrongName.h</span></span>

<span data-ttu-id="aceb6-119">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="aceb6-119">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="aceb6-120">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aceb6-120">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="aceb6-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="aceb6-121">See also</span></span>

- [<span data-ttu-id="aceb6-122">Método GetHashFromBlob</span><span class="sxs-lookup"><span data-stu-id="aceb6-122">GetHashFromBlob Method</span></span>](../hosting/iclrstrongname-gethashfromblob-method.md)
- [<span data-ttu-id="aceb6-123">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="aceb6-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
