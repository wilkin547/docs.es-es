---
description: 'Más información acerca de: StrongNameKeyDelete ((función)'
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
ms.openlocfilehash: 9314d961f79e673925125c2362308f9ab4533e75
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99781212"
---
# <a name="strongnamekeydelete-function"></a><span data-ttu-id="41728-103">StrongNameKeyDelete (Función)</span><span class="sxs-lookup"><span data-stu-id="41728-103">StrongNameKeyDelete Function</span></span>

<span data-ttu-id="41728-104">Elimina el contenedor de claves especificado.</span><span class="sxs-lookup"><span data-stu-id="41728-104">Deletes the specified key container.</span></span>

<span data-ttu-id="41728-105">Esta función está en desuso.</span><span class="sxs-lookup"><span data-stu-id="41728-105">This function has been deprecated.</span></span> <span data-ttu-id="41728-106">Use el método [ICLRStrongName:: StrongNameKeyDelete (](../hosting/iclrstrongname-strongnamekeydelete-method.md) en su lugar.</span><span class="sxs-lookup"><span data-stu-id="41728-106">Use the [ICLRStrongName::StrongNameKeyDelete](../hosting/iclrstrongname-strongnamekeydelete-method.md) method instead.</span></span>

## <a name="syntax"></a><span data-ttu-id="41728-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="41728-107">Syntax</span></span>

```cpp
BOOLEAN StrongNameKeyDelete (
    [in]  LPCWSTR   wszKeyContainer
);
```

## <a name="parameters"></a><span data-ttu-id="41728-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="41728-108">Parameters</span></span>

`wszKeyContainer`\
<span data-ttu-id="41728-109">de Nombre del contenedor de claves que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="41728-109">[in] The name of the key container to delete.</span></span>

## <a name="return-value"></a><span data-ttu-id="41728-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="41728-110">Return Value</span></span>

<span data-ttu-id="41728-111">`true` Cuando se complete correctamente; en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="41728-111">`true` on successful completion; otherwise, `false`.</span></span>

## <a name="remarks"></a><span data-ttu-id="41728-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="41728-112">Remarks</span></span>

<span data-ttu-id="41728-113">Utilice la función [StrongNameKeyInstall (](strongnamekeyinstall-function.md) para importar un par de claves pública y privada en un contenedor.</span><span class="sxs-lookup"><span data-stu-id="41728-113">Use the [StrongNameKeyInstall](strongnamekeyinstall-function.md) function to import a public/private key pair into a container.</span></span>

<span data-ttu-id="41728-114">Si la `StrongNameKeyDelete` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.</span><span class="sxs-lookup"><span data-stu-id="41728-114">If the `StrongNameKeyDelete` function does not complete successfully, call the [StrongNameErrorInfo](strongnameerrorinfo-function.md) function to retrieve the last generated error.</span></span>

## <a name="requirements"></a><span data-ttu-id="41728-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="41728-115">Requirements</span></span>

<span data-ttu-id="41728-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="41728-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="41728-117">**Encabezado:** StrongName. h</span><span class="sxs-lookup"><span data-stu-id="41728-117">**Header:** StrongName.h</span></span>

<span data-ttu-id="41728-118">**Biblioteca:** Se incluye como un recurso en MsCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="41728-118">**Library:** Included as a resource in MsCorEE.dll</span></span>

<span data-ttu-id="41728-119">**.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="41728-119">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="41728-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="41728-120">See also</span></span>

- [<span data-ttu-id="41728-121">Método StrongNameKeyDelete</span><span class="sxs-lookup"><span data-stu-id="41728-121">StrongNameKeyDelete Method</span></span>](../hosting/iclrstrongname-strongnamekeydelete-method.md)
- [<span data-ttu-id="41728-122">Método StrongNameKeyInstall</span><span class="sxs-lookup"><span data-stu-id="41728-122">StrongNameKeyInstall Method</span></span>](../hosting/iclrstrongname-strongnamekeyinstall-method.md)
- [<span data-ttu-id="41728-123">ICLRStrongName (Interfaz)</span><span class="sxs-lookup"><span data-stu-id="41728-123">ICLRStrongName Interface</span></span>](../hosting/iclrstrongname-interface.md)
