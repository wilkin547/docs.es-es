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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 353898b72f41acd0c49a43ff05e54f61b99444c4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798997"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="ab064-102">StrongNameKeyInstall (Función)</span><span class="sxs-lookup"><span data-stu-id="ab064-102">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="ab064-103">Importa un par de claves pública y privada a un contenedor.</span><span class="sxs-lookup"><span data-stu-id="ab064-103">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="ab064-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="ab064-104">This function has been deprecated.</span></span> <span data-ttu-id="ab064-105">Use el método [ICLRStrongName:: StrongNameKeyInstall (](../hosting/iclrstrongname-strongnamekeyinstall-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="ab064-105">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="ab064-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ab064-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="ab064-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ab064-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="ab064-108">de Nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="ab064-108">[in] The name of the key container.</span></span> <span data-ttu-id="ab064-109">`wszKeyContainer`debe ser una cadena no vacía.</span><span class="sxs-lookup"><span data-stu-id="ab064-109">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="ab064-110">de Par de claves binarias.</span><span class="sxs-lookup"><span data-stu-id="ab064-110">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="ab064-111">de Tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="ab064-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="ab064-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ab064-112">Return Value</span></span>

<span data-ttu-id="ab064-113">`true`Cuando se complete correctamente; en caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="ab064-113">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="ab064-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="ab064-114">Remarks</span></span>

<span data-ttu-id="ab064-115">Use la función [StrongNameKeyDelete (](strongnamekeydelete-function.md) para eliminar el contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="ab064-115">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="ab064-116">Si la `StrongNameKeyInstall` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="ab064-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="ab064-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ab064-117">Requirements</span></span>

<span data-ttu-id="ab064-118">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ab064-118">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="ab064-119">**Encabezado**: StrongName. h</span><span class="sxs-lookup"><span data-stu-id="ab064-119">**Header:** StrongName.h</span></span>

<span data-ttu-id="ab064-120">**Biblioteca** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="ab064-120">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="ab064-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ab064-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="ab064-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="ab064-122">See also</span></span>

- [<span data-ttu-id="ab064-123">StrongNameKeyInstall (método)</span><span class="sxs-lookup"><span data-stu-id="ab064-123">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="ab064-124">StrongNameKeyDelete (método)</span><span class="sxs-lookup"><span data-stu-id="ab064-124">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="ab064-125">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="ab064-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
