---
title: StrongNameKeyInstall (Función)
ms.date: 03/30/2017
api_name:
- StrongNameKeyInstall
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyInstall
helpviewer_keywords:
- StrongNameKeyInstall function [.NET Framework strong naming]
ms.assetid: e32fd546-7757-4681-be3d-658e93281e50
topic_type:
- apiref
ms.openlocfilehash: 9e441d4da64e9704fbda2368d2b07289aaea610a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73125197"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="45374-102">StrongNameKeyInstall (Función)</span><span class="sxs-lookup"><span data-stu-id="45374-102">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="45374-103">Importa un par de claves pública y privada a un contenedor.</span><span class="sxs-lookup"><span data-stu-id="45374-103">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="45374-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="45374-104">This function has been deprecated.</span></span> <span data-ttu-id="45374-105">Use el método [ICLRStrongName:: StrongNameKeyInstall (](../hosting/iclrstrongname-strongnamekeyinstall-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="45374-105">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="45374-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="45374-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="45374-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="45374-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="45374-108">de Nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="45374-108">[in] The name of the key container.</span></span> <span data-ttu-id="45374-109">`wszKeyContainer` debe ser una cadena no vacía.</span><span class="sxs-lookup"><span data-stu-id="45374-109">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="45374-110">de Par de claves binarias.</span><span class="sxs-lookup"><span data-stu-id="45374-110">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="45374-111">de Tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="45374-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="45374-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="45374-112">Return Value</span></span>

<span data-ttu-id="45374-113">`true` cuando se complete correctamente; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="45374-113">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="45374-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="45374-114">Remarks</span></span>

<span data-ttu-id="45374-115">Use la función [StrongNameKeyDelete (](strongnamekeydelete-function.md) para eliminar el contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="45374-115">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="45374-116">Si la función `StrongNameKeyInstall` no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="45374-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="45374-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="45374-117">Requirements</span></span>

<span data-ttu-id="45374-118">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="45374-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="45374-119">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="45374-119">**Header:** StrongName.h</span></span>

<span data-ttu-id="45374-120">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="45374-120">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="45374-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="45374-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="45374-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="45374-122">See also</span></span>

- [<span data-ttu-id="45374-123">StrongNameKeyInstall (método)</span><span class="sxs-lookup"><span data-stu-id="45374-123">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="45374-124">StrongNameKeyDelete (método)</span><span class="sxs-lookup"><span data-stu-id="45374-124">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="45374-125">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="45374-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
