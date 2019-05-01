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
ms.openlocfilehash: 6b3fc69b2edf611383402b13555cf33be10dbad3
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62000394"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="a9c6d-102">StrongNameKeyInstall (Función)</span><span class="sxs-lookup"><span data-stu-id="a9c6d-102">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="a9c6d-103">Importa un par de claves pública y privada a un contenedor.</span><span class="sxs-lookup"><span data-stu-id="a9c6d-103">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="a9c6d-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="a9c6d-104">This function has been deprecated.</span></span> <span data-ttu-id="a9c6d-105">Use la [ICLRStrongName](../hosting/iclrstrongname-strongnamekeyinstall-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="a9c6d-105">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="a9c6d-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="a9c6d-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="a9c6d-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="a9c6d-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="a9c6d-108">[in] Nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="a9c6d-108">[in] The name of the key container.</span></span> <span data-ttu-id="a9c6d-109">`wszKeyContainer` debe ser una cadena no vacía.</span><span class="sxs-lookup"><span data-stu-id="a9c6d-109">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="a9c6d-110">[in] El par de claves binario.</span><span class="sxs-lookup"><span data-stu-id="a9c6d-110">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="a9c6d-111">[in] El tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="a9c6d-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="a9c6d-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="a9c6d-112">Return Value</span></span>

<span data-ttu-id="a9c6d-113">`true` Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="a9c6d-113">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="a9c6d-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="a9c6d-114">Remarks</span></span>

<span data-ttu-id="a9c6d-115">Use la [StrongNameKeyDelete](strongnamekeydelete-function.md) función para eliminar el contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="a9c6d-115">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="a9c6d-116">Si el `StrongNameKeyInstall` función no se completa correctamente, llame a la [StrongNameErrorInfo](strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="a9c6d-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="a9c6d-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="a9c6d-117">Requirements</span></span>

<span data-ttu-id="a9c6d-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="a9c6d-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="a9c6d-119">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="a9c6d-119">**Header:** StrongName.h</span></span>

<span data-ttu-id="a9c6d-120">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="a9c6d-120">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="a9c6d-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a9c6d-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="a9c6d-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="a9c6d-122">See also</span></span>

- [<span data-ttu-id="a9c6d-123">StrongNameKeyInstall (método)</span><span class="sxs-lookup"><span data-stu-id="a9c6d-123">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="a9c6d-124">StrongNameKeyDelete (método)</span><span class="sxs-lookup"><span data-stu-id="a9c6d-124">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="a9c6d-125">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="a9c6d-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)