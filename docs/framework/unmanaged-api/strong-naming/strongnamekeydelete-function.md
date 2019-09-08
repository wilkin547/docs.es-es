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
ms.openlocfilehash: 17d35193f69966e02ac5e483924fcb3ee2e06758
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799019"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="764fd-102">StrongNameKeyDelete (Función)</span><span class="sxs-lookup"><span data-stu-id="764fd-102">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="764fd-103">Elimina el contenedor de claves especificado.</span><span class="sxs-lookup"><span data-stu-id="764fd-103">Deletes the specified key container.</span></span>

<span data-ttu-id="764fd-104">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="764fd-104">This function has been deprecated.</span></span> <span data-ttu-id="764fd-105">Use el método [ICLRStrongName:: StrongNameKeyDelete (](../hosting/iclrstrongname-strongnamekeydelete-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="764fd-105">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="764fd-106">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="764fd-106">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="764fd-107">Parámetros</span><span class="sxs-lookup"><span data-stu-id="764fd-107">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="764fd-108">de Nombre del contenedor de claves que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="764fd-108">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="764fd-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="764fd-109">Return Value</span></span>

<span data-ttu-id="764fd-110">`true`Cuando se complete correctamente; en caso `false`contrario,.</span><span class="sxs-lookup"><span data-stu-id="764fd-110">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="764fd-111">Comentarios</span><span class="sxs-lookup"><span data-stu-id="764fd-111">Remarks</span></span>

<span data-ttu-id="764fd-112">Utilice la función [StrongNameKeyInstall (](strongnamekeyinstall-function.md) para importar un par de claves pública y privada en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="764fd-112">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="764fd-113">Si la `StrongNameKeyDelete` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="764fd-113">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="764fd-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="764fd-114">Requirements</span></span>

<span data-ttu-id="764fd-115">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="764fd-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="764fd-116">**Encabezado**: StrongName. h</span><span class="sxs-lookup"><span data-stu-id="764fd-116">**Header:** StrongName.h</span></span>

<span data-ttu-id="764fd-117">**Biblioteca** Se incluye como recurso en MsCorEE. dll</span><span class="sxs-lookup"><span data-stu-id="764fd-117">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="764fd-118">**Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="764fd-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="764fd-119">Vea también</span><span class="sxs-lookup"><span data-stu-id="764fd-119">See also</span></span>

- [<span data-ttu-id="764fd-120">StrongNameKeyDelete (método)</span><span class="sxs-lookup"><span data-stu-id="764fd-120">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="764fd-121">StrongNameKeyInstall (método)</span><span class="sxs-lookup"><span data-stu-id="764fd-121">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="764fd-122">ICLRStrongName (interfaz)</span><span class="sxs-lookup"><span data-stu-id="764fd-122">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
