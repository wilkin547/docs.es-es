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
ms.openlocfilehash: d37f990241ae704abef55d863da0f40a31284837
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141586"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="14f84-102">StrongNameKeyDelete (Función)</span><span class="sxs-lookup"><span data-stu-id="14f84-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="14f84-103">Elimina el contenedor de claves especificado.</span><span class="sxs-lookup"><span data-stu-id="14f84-103">Deletes the specified key container.</span></span>

<span data-ttu-id="14f84-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="14f84-104">This function has been deprecated.</span></span> <span data-ttu-id="14f84-105">Use el método [ICLRStrongName:: StrongNameKeyDelete (](../hosting/iclrstrongname-strongnamekeydelete-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="14f84-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="14f84-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14f84-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="14f84-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="14f84-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="14f84-108">de Nombre del contenedor de claves que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="14f84-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="14f84-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="14f84-109">Return Value</span></span>

<span data-ttu-id="14f84-110">`true` cuando se complete correctamente; de lo contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="14f84-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="14f84-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="14f84-111">Remarks</span></span>

<span data-ttu-id="14f84-112">Utilice la función [StrongNameKeyInstall (](strongnamekeyinstall-function.md) para importar un par de claves pública y privada en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="14f84-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="14f84-113">Si la función `StrongNameKeyDelete` no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="14f84-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="14f84-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14f84-114">Requirements</span></span>

<span data-ttu-id="14f84-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14f84-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="14f84-116">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="14f84-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="14f84-117">**Biblioteca:** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="14f84-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="14f84-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="14f84-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="14f84-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="14f84-119">See also</span></span>

- [<span data-ttu-id="14f84-120">StrongNameKeyDelete (método)</span><span class="sxs-lookup"><span data-stu-id="14f84-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="14f84-121">StrongNameKeyInstall (método)</span><span class="sxs-lookup"><span data-stu-id="14f84-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="14f84-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="14f84-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
