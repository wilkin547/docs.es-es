---
title: 'IXCLRDataModule:: GetMethodDefinitionByToken (método)'
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::GetMethodDefinitionByToken Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method
helpviewer.keywords:
- IXCLRDataModule::GetMethodDefinitionByToken Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: c70920205b27376d453bdd0a13223c6a5569075b
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83395296"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="07aef-102">IXCLRDataModule:: GetMethodDefinitionByToken (método)</span><span class="sxs-lookup"><span data-stu-id="07aef-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="07aef-103">Obtiene la definición de método correspondiente a un token de metadatos determinado.</span><span class="sxs-lookup"><span data-stu-id="07aef-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="07aef-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="07aef-104">Syntax</span></span>

```cpp
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="07aef-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="07aef-105">Parameters</span></span>

`token`\
<span data-ttu-id="07aef-106">de Token del método.</span><span class="sxs-lookup"><span data-stu-id="07aef-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="07aef-107">enuncia La definición del método.</span><span class="sxs-lookup"><span data-stu-id="07aef-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="07aef-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="07aef-108">Remarks</span></span>

<span data-ttu-id="07aef-109">El método proporcionado forma parte de la `IXCLRDataModule` interfaz y corresponde a la ranura del 26 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="07aef-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 26th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="07aef-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="07aef-110">Requirements</span></span>

<span data-ttu-id="07aef-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="07aef-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="07aef-112">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="07aef-112">**Header:** None</span></span>  
<span data-ttu-id="07aef-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="07aef-113">**Library:** None</span></span>  
<span data-ttu-id="07aef-114">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="07aef-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="07aef-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="07aef-115">See also</span></span>

- [<span data-ttu-id="07aef-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="07aef-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="07aef-117">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="07aef-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
