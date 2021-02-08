---
description: 'Más información sobre: ISOSDacInterface:: GetMethodDescPtrFromIP (método)'
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
ms.openlocfilehash: 8d7c7071b7b3fc520faea71c8d7792317745cfde
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790417"
---
# <a name="isosdacinterfacegetmethoddescptrfromip-method"></a><span data-ttu-id="0f264-103">ISOSDacInterface:: GetMethodDescPtrFromIP (método)</span><span class="sxs-lookup"><span data-stu-id="0f264-103">ISOSDacInterface::GetMethodDescPtrFromIP Method</span></span>

<span data-ttu-id="0f264-104">Recupera el puntero de la MethodDesc correspondiente al método que contiene la dirección de instrucción nativa especificada.</span><span class="sxs-lookup"><span data-stu-id="0f264-104">Retrieves the pointer of the MethodDesc corresponding the method containing the given native instruction address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="0f264-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0f264-105">Syntax</span></span>

```cpp
HRESULT GetMethodDescPtrFromIP(
    CLRDATA_ADDRESS ip,
    CLRDATA_ADDRESS * ppMD
);
```

## <a name="parameters"></a><span data-ttu-id="0f264-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0f264-106">Parameters</span></span>

`ip`\
<span data-ttu-id="0f264-107">de Una dirección dentro del método en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0f264-107">[in] An address within the method at runtime.</span></span>

`ppMD`\
<span data-ttu-id="0f264-108">enuncia La dirección de `MethodDesc` para el método determinado.</span><span class="sxs-lookup"><span data-stu-id="0f264-108">[out] The address of the `MethodDesc` for the particular method.</span></span>

## <a name="remarks"></a><span data-ttu-id="0f264-109">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0f264-109">Remarks</span></span>

<span data-ttu-id="0f264-110">El método proporcionado forma parte de la [ `ISOSDacInterface` interfaz](isosdacinterface-interface.md) y corresponde a la ranura 22 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="0f264-110">The provided method is part of the [`ISOSDacInterface` interface](isosdacinterface-interface.md) and corresponds to the 22nd slot of the virtual method table.</span></span>

## <a name="requirements"></a><span data-ttu-id="0f264-111">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0f264-111">Requirements</span></span>

<span data-ttu-id="0f264-112">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0f264-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="0f264-113">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="0f264-113">**Header:** None</span></span>  
<span data-ttu-id="0f264-114">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="0f264-114">**Library:** None</span></span>  
<span data-ttu-id="0f264-115">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0f264-115">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="0f264-116">Vea también</span><span class="sxs-lookup"><span data-stu-id="0f264-116">See also</span></span>

- [<span data-ttu-id="0f264-117">Depuración</span><span class="sxs-lookup"><span data-stu-id="0f264-117">Debugging</span></span>](index.md)
- [<span data-ttu-id="0f264-118">Interfaz ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="0f264-118">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
