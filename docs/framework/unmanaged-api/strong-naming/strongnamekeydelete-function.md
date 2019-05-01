---
title: StrongNameKeyDelete (Función)
ms.date: 03/30/2017
api_name:
- StrongNameKeyDelete
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameKeyDelete
helpviewer_keywords:
- StrongNameKeyDelete function [.NET Framework strong naming]
ms.assetid: 313e71e4-1790-4d2f-b68b-5040ebd1c149
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: dfc785a48d0cdf1cf2fdc0245a27b8ef35fd2d81
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "62040773"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="c38de-102">StrongNameKeyDelete (Función)</span><span class="sxs-lookup"><span data-stu-id="c38de-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="c38de-103">Elimina el contenedor de claves especificado.</span><span class="sxs-lookup"><span data-stu-id="c38de-103">Deletes the specified key container.</span></span>

<span data-ttu-id="c38de-104">Esta función está desusada.</span><span class="sxs-lookup"><span data-stu-id="c38de-104">This function has been deprecated.</span></span> <span data-ttu-id="c38de-105">Use la [ICLRStrongName](../hosting/iclrstrongname-strongnamekeydelete-method.md) método en su lugar.</span><span class="sxs-lookup"><span data-stu-id="c38de-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="c38de-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c38de-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="c38de-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c38de-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="c38de-108">[in] Nombre del contenedor de claves para eliminar.</span><span class="sxs-lookup"><span data-stu-id="c38de-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="c38de-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c38de-109">Return Value</span></span>

<span data-ttu-id="c38de-110">`true` Cuando se finaliza correctamente; en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="c38de-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="c38de-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c38de-111">Remarks</span></span>

<span data-ttu-id="c38de-112">Use la [StrongNameKeyInstall](strongnamekeyinstall-function.md) función para importar un par de claves pública y privada en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="c38de-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="c38de-113">Si el `StrongNameKeyDelete` función no se completa correctamente, llame a la [StrongNameErrorInfo](strongnameerrorinfo-function.md) función para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="c38de-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="c38de-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c38de-114">Requirements</span></span>

<span data-ttu-id="c38de-115">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c38de-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="c38de-116">**Encabezado**: StrongName.h</span><span class="sxs-lookup"><span data-stu-id="c38de-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="c38de-117">**Biblioteca:** Incluye como recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="c38de-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="c38de-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c38de-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c38de-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="c38de-119">See also</span></span>

- [<span data-ttu-id="c38de-120">StrongNameKeyDelete (método)</span><span class="sxs-lookup"><span data-stu-id="c38de-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="c38de-121">StrongNameKeyInstall (método)</span><span class="sxs-lookup"><span data-stu-id="c38de-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="c38de-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="c38de-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)