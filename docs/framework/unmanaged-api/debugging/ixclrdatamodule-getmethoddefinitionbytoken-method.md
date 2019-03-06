---
title: Método IXCLRDataModule::GetMethodDefinitionByToken
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
ms.openlocfilehash: 727005437289b4bc66ab90f280b80a79f4db06db
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57359320"
---
# <a name="ixclrdatamodulegetmethoddefinitionbytoken-method"></a><span data-ttu-id="5a521-102">Método IXCLRDataModule::GetMethodDefinitionByToken</span><span class="sxs-lookup"><span data-stu-id="5a521-102">IXCLRDataModule::GetMethodDefinitionByToken Method</span></span>

<span data-ttu-id="5a521-103">Obtiene la definición del método correspondiente a un token de metadatos especificado.</span><span class="sxs-lookup"><span data-stu-id="5a521-103">Gets the method definition corresponding to a given metadata token.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5a521-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5a521-104">Syntax</span></span>

```
HRESULT GetMethodDefinitionByToken(
    [in] mdMethodDef token,
    [out] IXCLRDataMethodDefinition** methodDefinition
);
```

## <a name="parameters"></a><span data-ttu-id="5a521-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5a521-105">Parameters</span></span>

`token`\
<span data-ttu-id="5a521-106">[in] El token del método.</span><span class="sxs-lookup"><span data-stu-id="5a521-106">[in] The method token.</span></span>

`methodDefinition`\
<span data-ttu-id="5a521-107">[out] La definición del método.</span><span class="sxs-lookup"><span data-stu-id="5a521-107">[out] The method definition.</span></span>

## <a name="remarks"></a><span data-ttu-id="5a521-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5a521-108">Remarks</span></span>

<span data-ttu-id="5a521-109">El método proporcionado forma parte de la `IXCLRDataModule` interfaz y corresponde a la ranura de la tabla de métodos virtuales 25.</span><span class="sxs-lookup"><span data-stu-id="5a521-109">The provided method is part of the `IXCLRDataModule` interface and corresponds to the 25th slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="5a521-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5a521-110">Requirements</span></span>

<span data-ttu-id="5a521-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5a521-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5a521-112">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="5a521-112">**Header:** None</span></span>  
<span data-ttu-id="5a521-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="5a521-113">**Library:** None</span></span>  
<span data-ttu-id="5a521-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5a521-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  
 
## <a name="see-also"></a><span data-ttu-id="5a521-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5a521-115">See also</span></span>

- [<span data-ttu-id="5a521-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="5a521-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="5a521-117">Interfaz IXCLRDataModule</span><span class="sxs-lookup"><span data-stu-id="5a521-117">IXCLRDataModule Interface</span></span>](ixclrdatamodule-interface.md)
