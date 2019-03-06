---
title: Método IXCLRDataProcess::EndEnumModules
ms.date: 01/16/2019
api.name:
- IXCLRDataProcess::EndEnumModules Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::EndEnumModules Method
helpviewer.keywords:
- IXCLRDataProcess::EndEnumModules Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 3b7050e92af6fc58b45837840b2796a5deac955c
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57375342"
---
# <a name="ixclrdataprocessendenummodules-method"></a><span data-ttu-id="71676-102">Método IXCLRDataProcess::EndEnumModules</span><span class="sxs-lookup"><span data-stu-id="71676-102">IXCLRDataProcess::EndEnumModules Method</span></span>

<span data-ttu-id="71676-103">Libera los recursos utilizados por los iteradores internos usa durante la enumeración de módulo.</span><span class="sxs-lookup"><span data-stu-id="71676-103">Releases the resources used by internal iterators used during module enumeration.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="71676-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="71676-104">Syntax</span></span>
```
HRESULT EndEnumModules(
    [in] CLRDATA_ENUM handle
);
```

## <a name="parameters"></a><span data-ttu-id="71676-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="71676-105">Parameters</span></span>

`handle`\
<span data-ttu-id="71676-106">[out] Un identificador para enumerar los módulos.</span><span class="sxs-lookup"><span data-stu-id="71676-106">[out] A handle for enumerating the modules.</span></span>

## <a name="remarks"></a><span data-ttu-id="71676-107">Comentarios</span><span class="sxs-lookup"><span data-stu-id="71676-107">Remarks</span></span>

<span data-ttu-id="71676-108">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura de la tabla de métodos virtuales 26.</span><span class="sxs-lookup"><span data-stu-id="71676-108">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="71676-109">Requisitos</span><span class="sxs-lookup"><span data-stu-id="71676-109">Requirements</span></span>

<span data-ttu-id="71676-110">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="71676-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>   
<span data-ttu-id="71676-111">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="71676-111">**Header:** None</span></span>   
<span data-ttu-id="71676-112">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="71676-112">**Library:** None</span></span>   
<span data-ttu-id="71676-113">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="71676-113">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>   

## <a name="see-also"></a><span data-ttu-id="71676-114">Vea también</span><span class="sxs-lookup"><span data-stu-id="71676-114">See also</span></span>

- [<span data-ttu-id="71676-115">Depuración</span><span class="sxs-lookup"><span data-stu-id="71676-115">Debugging</span></span>](index.md)
- [<span data-ttu-id="71676-116">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="71676-116">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
