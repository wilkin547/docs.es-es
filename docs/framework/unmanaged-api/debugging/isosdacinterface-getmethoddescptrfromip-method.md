---
title: 'ISOSDacInterface:: GetMethodDescPtrFromIP (método)'
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
ms.openlocfilehash: 0c8d91c11205e06857b4a6e7edfedcd087270d00
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396934"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="55371-102">ISOSDacInterface:: GetMethodDescPtrFromIP (método)</span><span class="sxs-lookup"><span data-stu-id="55371-102">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="55371-103">Recupera el puntero de la MethodDesc correspondiente al método que contiene la dirección de instrucción nativa especificada.</span><span class="sxs-lookup"><span data-stu-id="55371-103">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="55371-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="55371-104">Syntax</span></span>

```cpp
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a><span data-ttu-id="55371-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="55371-105">Parameters</span></span>

`ip`\
<span data-ttu-id="55371-106">de Una dirección dentro del método en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="55371-106">[in] An address within the method at runtime.</span></span>

`ppMD`\
<span data-ttu-id="55371-107">enuncia La dirección de `MethodDesc` para el método determinado.</span><span class="sxs-lookup"><span data-stu-id="55371-107">[out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="55371-108">Comentarios</span><span class="sxs-lookup"><span data-stu-id="55371-108">Remarks</span></span>

<span data-ttu-id="55371-109">El método proporcionado forma parte de la [ `ISOSDacInterface` interfaz](isosdacinterface-interface.md) y corresponde a la ranura 22 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="55371-109">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 22nd slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="55371-110">Requisitos</span><span class="sxs-lookup"><span data-stu-id="55371-110">Requirements</span></span>

<span data-ttu-id="55371-111">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="55371-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="55371-112">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="55371-112">**Header:** None</span></span>  
<span data-ttu-id="55371-113">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="55371-113">**Library:** None</span></span>  
<span data-ttu-id="55371-114">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="55371-114">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="55371-115">Vea también</span><span class="sxs-lookup"><span data-stu-id="55371-115">See also</span></span>

- [<span data-ttu-id="55371-116">Depuración</span><span class="sxs-lookup"><span data-stu-id="55371-116">Debugging</span></span>](index.md)
- [<span data-ttu-id="55371-117">Interfaz ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="55371-117">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
