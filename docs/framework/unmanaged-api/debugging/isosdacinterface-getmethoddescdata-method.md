---
title: 'ISOSDacInterface:: GetMethodDescData (método)'
ms.date: 01/16/2019
api.name:
- ISOSDacInterface::GetMethodDescData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescData Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescData Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 105149d0abf312c33a8498e7428e3a8b23d6ae7d
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/15/2020
ms.locfileid: "83421025"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="0de31-102">ISOSDacInterface:: GetMethodDescData (método)</span><span class="sxs-lookup"><span data-stu-id="0de31-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="0de31-103">Obtiene los datos para el puntero de MethodDesc dado.</span><span class="sxs-lookup"><span data-stu-id="0de31-103">Gets the data for the given MethodDesc pointer.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="0de31-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0de31-104">Syntax</span></span>

```cpp
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

## <a name="parameters"></a><span data-ttu-id="0de31-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0de31-105">Parameters</span></span>

`methodDesc`\
<span data-ttu-id="0de31-106">de Dirección de la MethodDesc.</span><span class="sxs-lookup"><span data-stu-id="0de31-106">[in] The address of the MethodDesc.</span></span>

`ip`\
<span data-ttu-id="0de31-107">de Dirección IP del método.</span><span class="sxs-lookup"><span data-stu-id="0de31-107">[in] The IP address of the method.</span></span>

`data`\
<span data-ttu-id="0de31-108">enuncia Los datos asociados al MethodDesc tal y como se devuelven desde las API internas.</span><span class="sxs-lookup"><span data-stu-id="0de31-108">[out] The data associated with the MethodDesc as returned from the internal APIs.</span></span>

`cRevertedRejitVersions`\
<span data-ttu-id="0de31-109">enuncia Número de versiones revertidas de rejit.</span><span class="sxs-lookup"><span data-stu-id="0de31-109">[out] The number of reverted rejit versions.</span></span>

`rgRevertedRejitData`\
<span data-ttu-id="0de31-110">enuncia Los datos asociados a las versiones revertidas de rejit devueltas por las API internas.</span><span class="sxs-lookup"><span data-stu-id="0de31-110">[out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span>

`pcNeededRevertedRejitData`\
<span data-ttu-id="0de31-111">enuncia El número de bytes necesarios para almacenar los datos asociados a las versiones revertidas de ReJit.</span><span class="sxs-lookup"><span data-stu-id="0de31-111">[out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="0de31-112">Observaciones</span><span class="sxs-lookup"><span data-stu-id="0de31-112">Remarks</span></span>

<span data-ttu-id="0de31-113">El método proporcionado forma parte de la `ISOSDacInterface` interfaz y corresponde a la ranura 21 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="0de31-113">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 21st slot of the virtual method table.</span></span> <span data-ttu-id="0de31-114">Para poder utilizarlos, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) debe definirse como un entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="0de31-114">To be able to use them, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) must be defined as a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="0de31-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0de31-115">Requirements</span></span>

<span data-ttu-id="0de31-116">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="0de31-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="0de31-117">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="0de31-117">**Header:** None</span></span>  
<span data-ttu-id="0de31-118">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="0de31-118">**Library:** None</span></span>  
<span data-ttu-id="0de31-119">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0de31-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="0de31-120">Consulta también</span><span class="sxs-lookup"><span data-stu-id="0de31-120">See also</span></span>

- [<span data-ttu-id="0de31-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="0de31-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="0de31-122">Interfaz ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="0de31-122">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
