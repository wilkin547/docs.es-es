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
ms.openlocfilehash: 7121ace6777e7cf947fcc6ff30b1ea314851feff
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2019
ms.locfileid: "65636713"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="4e2a2-102">StrongNameKeyInstall (Función)</span><span class="sxs-lookup"><span data-stu-id="4e2a2-102">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="4e2a2-103">Importa un par de claves pública y privada a un contenedor.</span><span class="sxs-lookup"><span data-stu-id="4e2a2-103">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="4e2a2-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="4e2a2-104">This function has been deprecated.</span></span> <span data-ttu-id="4e2a2-105">Use la [ICLRStrongName](../hosting/iclrstrongname-strongnamekeyinstall-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="4e2a2-105">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="4e2a2-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4e2a2-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="4e2a2-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4e2a2-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="4e2a2-108">[in] Nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="4e2a2-108">[in] The name of the key container.</span></span> <span data-ttu-id="4e2a2-109">`wszKeyContainer` debe ser una cadena no vacía.</span><span class="sxs-lookup"><span data-stu-id="4e2a2-109">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="4e2a2-110">[in] El par de claves binario.</span><span class="sxs-lookup"><span data-stu-id="4e2a2-110">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="4e2a2-111">[in] El tamaño, en bytes, de `pbKeyBlob`.</span><span class="sxs-lookup"><span data-stu-id="4e2a2-111">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="4e2a2-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4e2a2-112">Return Value</span></span>

<span data-ttu-id="4e2a2-113">`true` Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="4e2a2-113">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="4e2a2-114">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4e2a2-114">Remarks</span></span>

<span data-ttu-id="4e2a2-115">Use la [StrongNameKeyDelete](strongnamekeydelete-function.md) función para eliminar el contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="4e2a2-115">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="4e2a2-116">Si el `StrongNameKeyInstall` función no se completa correctamente, llame a la [StrongNameErrorInfo](strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="4e2a2-116">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="4e2a2-117">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4e2a2-117">Requirements</span></span>

<span data-ttu-id="4e2a2-118">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4e2a2-118">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="4e2a2-119">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="4e2a2-119">**Header:** StrongName.h</span></span>

<span data-ttu-id="4e2a2-120">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="4e2a2-120">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="4e2a2-121">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4e2a2-121">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4e2a2-122">Vea también</span><span class="sxs-lookup"><span data-stu-id="4e2a2-122">See also</span></span>

- [<span data-ttu-id="4e2a2-123">StrongNameKeyInstall (método)</span><span class="sxs-lookup"><span data-stu-id="4e2a2-123">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="4e2a2-124">StrongNameKeyDelete (método)</span><span class="sxs-lookup"><span data-stu-id="4e2a2-124">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="4e2a2-125">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="4e2a2-125">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
