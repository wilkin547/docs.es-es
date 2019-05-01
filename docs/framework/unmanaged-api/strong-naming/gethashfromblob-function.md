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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3d9e7b52c9061a1a7b470f9d4abf735e605087dc
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000537"
---
# <a name="gethashfromblob-function"></a><span data-ttu-id="ec895-102">GetHashFromBlob (Función)</span><span class="sxs-lookup"><span data-stu-id="ec895-102">GetHashFromBlob Function</span></span>

<span data-ttu-id="ec895-103">Obtiene un hash del ensamblado en la dirección de memoria especificada mediante un algoritmo hash concreto.</span><span class="sxs-lookup"><span data-stu-id="ec895-103">Gets a hash of the assembly at the specified memory address, using the specified hash algorithm.</span></span>

<span data-ttu-id="ec895-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="ec895-104">This function has been deprecated.</span></span> <span data-ttu-id="ec895-105">Use la [ICLRStrongName](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="ec895-105">Use the [ICLRStrongName::GetHashFromBlob](../../../../docs/framework/unmanaged-api/hosting/iclrstrongname-gethashfromblob-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="ec895-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ec895-106">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="ec895-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ec895-107">Parameters</span></span>

`pbBlob`\
<span data-ttu-id="ec895-108">[in] Un puntero a la dirección del bloque de memoria para un algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="ec895-108">[in] A pointer to the address of the memory block to be hashed.</span></span>

`cchBlob`\
<span data-ttu-id="ec895-109">[in] La longitud, en bytes, del bloque de memoria.</span><span class="sxs-lookup"><span data-stu-id="ec895-109">[in] The length, in bytes, of the memory block.</span></span>

`piHashAlg`\
<span data-ttu-id="ec895-110">[in, out] Una constante que especifica el algoritmo hash.</span><span class="sxs-lookup"><span data-stu-id="ec895-110">[in, out] A constant that specifies the hash algorithm.</span></span> <span data-ttu-id="ec895-111">Usar cero para el algoritmo predeterminado.</span><span class="sxs-lookup"><span data-stu-id="ec895-111">Use zero for the default algorithm.</span></span>

`pbHash`\
<span data-ttu-id="ec895-112">[out] El búfer hash devuelto.</span><span class="sxs-lookup"><span data-stu-id="ec895-112">[out] The returned hash buffer.</span></span>

`cchHash`\
<span data-ttu-id="ec895-113">[in] El tamaño máximo solicitado de `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="ec895-113">[in] The requested maximum size of `pbHash`.</span></span>

`pchHash`\
<span data-ttu-id="ec895-114">[out] El tamaño, en bytes, del devuelto `pbHash`.</span><span class="sxs-lookup"><span data-stu-id="ec895-114">[out] The size, in bytes, of the returned `pbHash`.</span></span>

## <a name="requirements"></a><span data-ttu-id="ec895-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ec895-115">Requirements</span></span>

<span data-ttu-id="ec895-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ec895-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="ec895-117">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="ec895-117">**Header:** StrongName.h</span></span>

<span data-ttu-id="ec895-118">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="ec895-118">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="ec895-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ec895-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ec895-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="ec895-120">See also</span></span>

- [<span data-ttu-id="ec895-121">GetHashFromBlob (método)</span><span class="sxs-lookup"><span data-stu-id="ec895-121">GetHashFromBlob Method</span></span>](../hosting/iclrstrongname-gethashfromblob-method.md)
- [<span data-ttu-id="ec895-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ec895-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)