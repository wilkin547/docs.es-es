---
title: Método ISOSDacInterface::GetMethodDescPtrFromIP
ms.date: 02/01/2019
api.name:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescPtrFromIP Method [.NET Framework debugging]
topic_type:
- apiref
author: hoyosjs
ms.author: juhoyosa
ms.openlocfilehash: 74853733b1fb7f023d9f192d3e862dbf6875ecda
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55828660"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="5371b-102">Método ISOSDacInterface::GetMethodDescPtrFromIP</span><span class="sxs-lookup"><span data-stu-id="5371b-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="5371b-103">Recupera el puntero de la MethodDesc correspondiente del método que contiene la dirección de instrucción nativo especificado.</span><span class="sxs-lookup"><span data-stu-id="5371b-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="5371b-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5371b-104">Syntax</span></span>

```
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

### <a name="parameters"></a><span data-ttu-id="5371b-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5371b-105">Parameters</span></span>

<span data-ttu-id="5371b-106">`ip` [in] Una dirección dentro del método en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="5371b-106">`ip` [in] An address within the method at runtime.</span></span>

<span data-ttu-id="5371b-107">`ppMD` [out] La dirección de la `MethodDesc` para el método concreto.</span><span class="sxs-lookup"><span data-stu-id="5371b-107">`ppMD` [out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="5371b-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5371b-108">Remarks</span></span>

<span data-ttu-id="5371b-109">El método proporcionado forma parte de la [ `ISOSDacInterface` interfaz](isosdacinterface-interface.md) y corresponde a la ranura de la tabla de métodos virtuales 21.</span><span class="sxs-lookup"><span data-stu-id="5371b-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 21st slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="5371b-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5371b-110">Requirements</span></span>

<span data-ttu-id="5371b-111">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5371b-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="5371b-112">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="5371b-112">**Header:** None</span></span>  
<span data-ttu-id="5371b-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="5371b-113">**Library:** None</span></span>  
<span data-ttu-id="5371b-114">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5371b-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="5371b-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="5371b-115">See also</span></span>

- [<span data-ttu-id="5371b-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="5371b-116">Debugging</span></span>](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [<span data-ttu-id="5371b-117">Interfaz ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="5371b-117">ISOSDacInterface Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md)
