---
description: 'Más información acerca de: StrongNameKeyInstall ((función)'
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
ms.openlocfilehash: 0a5d3971ac0927dda7066405adc01a5c80b7faca
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99670559"
---
# <a name="strongnamekeyinstall-function"></a><span data-ttu-id="b4c41-103">StrongNameKeyInstall (Función)</span><span class="sxs-lookup"><span data-stu-id="b4c41-103">StrongNameKeyInstall Function</span></span>

<span data-ttu-id="b4c41-104">Importa un par de claves pública y privada a un contenedor.</span><span class="sxs-lookup"><span data-stu-id="b4c41-104">Imports a public/private key pair into a container.</span></span>

<span data-ttu-id="b4c41-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="b4c41-105">This function has been deprecated.</span></span> <span data-ttu-id="b4c41-106">Use el método [ICLRStrongName:: StrongNameKeyInstall (](../hosting/iclrstrongname-strongnamekeyinstall-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="b4c41-106">Use the [ICLRStrongName::StrongNameKeyInstall](../hosting/iclrstrongname-strongnamekeyinstall-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="b4c41-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b4c41-107">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyInstall (
    [in]  LPCWSTR   wszKeyContainer,
    [in]  BYTE      *pbKeyBlob,
    [in]  ULONG     cbKeyBlob
);
```

## <a name="parameters"></a><span data-ttu-id="b4c41-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b4c41-108">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="b4c41-109">de Nombre del contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="b4c41-109">[in] The name of the key container.</span></span> <span data-ttu-id="b4c41-110">`wszKeyContainer` debe ser una cadena no vacía.</span><span class="sxs-lookup"><span data-stu-id="b4c41-110">`wszKeyContainer` must be a non-empty string.</span></span>

`pbKeyBlob`\
<span data-ttu-id="b4c41-111">de Par de claves binarias.</span><span class="sxs-lookup"><span data-stu-id="b4c41-111">[in] The binary key pair.</span></span>

`cbKeyBlob`\
<span data-ttu-id="b4c41-112">de Tamaño, en bytes, de `pbKeyBlob` .</span><span class="sxs-lookup"><span data-stu-id="b4c41-112">[in] The size, in bytes, of `pbKeyBlob`.</span></span>

## <a name="return-value"></a><span data-ttu-id="b4c41-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b4c41-113">Return Value</span></span>

<span data-ttu-id="b4c41-114">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="b4c41-114">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="b4c41-115">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b4c41-115">Remarks</span></span>

<span data-ttu-id="b4c41-116">Use la función [StrongNameKeyDelete (](strongnamekeydelete-function.md) para eliminar el contenedor de claves.</span><span class="sxs-lookup"><span data-stu-id="b4c41-116">Use the [StrongNameKeyDelete](strongnamekeydelete-function.md) function to delete the key container.</span></span>

<span data-ttu-id="b4c41-117">Si la `StrongNameKeyInstall` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="b4c41-117">If the `StrongNameKeyInstall` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="b4c41-118">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b4c41-118">Requirements</span></span>

<span data-ttu-id="b4c41-119">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b4c41-119">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="b4c41-120">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="b4c41-120">**Header:** StrongName.h</span></span>

<span data-ttu-id="b4c41-121">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="b4c41-121">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="b4c41-122">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="b4c41-122">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="b4c41-123">Vea también</span><span class="sxs-lookup"><span data-stu-id="b4c41-123">See also</span></span>

- [<span data-ttu-id="b4c41-124">Método StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="b4c41-124">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="b4c41-125">Método StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="b4c41-125">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="b4c41-126">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="b4c41-126">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
