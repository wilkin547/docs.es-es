---
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
ms.openlocfilehash: d1027aea1d800bda1654b223fec992aa70efd4b7
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73140715"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="d0bfa-102">GetHashFromBlob (Función)</span><span class="sxs-lookup"><span data-stu-id="d0bfa-102">GetHashFromBlob Function</span></span>

<span data-ttu-id="d0bfa-103">Obtiene un hash del ensamblado en la dirección de memoria especificada mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="d0bfa-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>

<span data-ttu-id="d0bfa-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="d0bfa-104">This function has been deprecated.</span></span> <span data-ttu-id="d0bfa-105">Use el método [ICLRStrongName:: GetHashFromBlob (](../hosting/iclrstrongname-gethashfromblob-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="d0bfa-105">Use the [ICLRStrongName::GetHashFromBlob](../hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="d0bfa-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="d0bfa-106">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="d0bfa-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="d0bfa-107">Parameters</span></span>

`pbBlob`\
<span data-ttu-id="d0bfa-108">de Puntero a la dirección del bloque de memoria al que se va a aplicar un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="d0bfa-108">[in] A pointer to the address of the memory block to be hashed.</span></span>

`cchBlob`\
<span data-ttu-id="d0bfa-109">de La longitud, en bytes, del bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="d0bfa-109">[in] The length, in bytes, of the memory block.</span></span>

`piHashAlg`\
<span data-ttu-id="d0bfa-110">[in, out] Constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="d0bfa-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="d0bfa-111">Use cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="d0bfa-111">Use zero for the default algorithm.</span></span>

`pbHash`\
<span data-ttu-id="d0bfa-112">enuncia Búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="d0bfa-112">[out] The returned hash buffer.</span></span>

`cchHash`\
<span data-ttu-id="d0bfa-113">de Tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="d0bfa-113">[in] The requested maximum size of `pbHash`.</span></span>

`pchHash`\
<span data-ttu-id="d0bfa-114">enuncia Tamaño, en bytes, del `pbHash`devuelto.</span><span class="sxs-lookup"><span data-stu-id="d0bfa-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>

## <a name="requirements"></a><span data-ttu-id="d0bfa-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="d0bfa-115">Requirements</span></span>

<span data-ttu-id="d0bfa-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="d0bfa-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="d0bfa-117">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="d0bfa-117">**Header:** StrongName.h</span></span>

<span data-ttu-id="d0bfa-118">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="d0bfa-118">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="d0bfa-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d0bfa-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="d0bfa-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="d0bfa-120">See also</span></span>

- [<span data-ttu-id="d0bfa-121">GetHashFromBlob (método)</span><span class="sxs-lookup"><span data-stu-id="d0bfa-121">GetHashFromBlob Method</span></span>](../hosting/iclrstrongname-gethashfromblob-method.md)
- [<span data-ttu-id="d0bfa-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="d0bfa-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
