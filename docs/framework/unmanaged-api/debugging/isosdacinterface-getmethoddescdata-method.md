---
description: 'Más información sobre: ISOSDacInterface:: GetMethodDescData (método)'
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
ms.openlocfilehash: a1284aa4d810ed9d6db7ad3c1b471702b1dad54d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790430"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="17114-103">ISOSDacInterface:: GetMethodDescData (método)</span><span class="sxs-lookup"><span data-stu-id="17114-103">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="17114-104">Obtiene los datos para el puntero de MethodDesc dado.</span><span class="sxs-lookup"><span data-stu-id="17114-104">Gets the data for the given MethodDesc pointer.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="17114-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="17114-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="17114-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="17114-106">Parameters</span></span>

`methodDesc`\
<span data-ttu-id="17114-107">de Dirección de la MethodDesc.</span><span class="sxs-lookup"><span data-stu-id="17114-107">[in] The address of the MethodDesc.</span></span>

`ip`\
<span data-ttu-id="17114-108">de Dirección IP del método.</span><span class="sxs-lookup"><span data-stu-id="17114-108">[in] The IP address of the method.</span></span>

`data`\
<span data-ttu-id="17114-109">enuncia Los datos asociados al MethodDesc tal y como se devuelven desde las API internas.</span><span class="sxs-lookup"><span data-stu-id="17114-109">[out] The data associated with the MethodDesc as returned from the internal APIs.</span></span>

`cRevertedRejitVersions`\
<span data-ttu-id="17114-110">enuncia Número de versiones revertidas de rejit.</span><span class="sxs-lookup"><span data-stu-id="17114-110">[out] The number of reverted rejit versions.</span></span>

`rgRevertedRejitData`\
<span data-ttu-id="17114-111">enuncia Los datos asociados a las versiones revertidas de rejit devueltas por las API internas.</span><span class="sxs-lookup"><span data-stu-id="17114-111">[out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span>

`pcNeededRevertedRejitData`\
<span data-ttu-id="17114-112">enuncia El número de bytes necesarios para almacenar los datos asociados a las versiones revertidas de ReJit.</span><span class="sxs-lookup"><span data-stu-id="17114-112">[out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="17114-113">Observaciones</span><span class="sxs-lookup"><span data-stu-id="17114-113">Remarks</span></span>

<span data-ttu-id="17114-114">El método proporcionado forma parte de la `ISOSDacInterface` interfaz y corresponde a la ranura 21 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="17114-114">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 21st slot of the virtual method table.</span></span> <span data-ttu-id="17114-115">Para poder utilizarlos, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) debe definirse como un entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="17114-115">To be able to use them, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) must be defined as a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="17114-116">Requisitos</span><span class="sxs-lookup"><span data-stu-id="17114-116">Requirements</span></span>

<span data-ttu-id="17114-117">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="17114-117">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
<span data-ttu-id="17114-118">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="17114-118">**Header:** None</span></span>  
<span data-ttu-id="17114-119">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="17114-119">**Library:** None</span></span>  
<span data-ttu-id="17114-120">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="17114-120">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="17114-121">Vea también</span><span class="sxs-lookup"><span data-stu-id="17114-121">See also</span></span>

- [<span data-ttu-id="17114-122">Depuración</span><span class="sxs-lookup"><span data-stu-id="17114-122">Debugging</span></span>](index.md)
- [<span data-ttu-id="17114-123">Interfaz ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="17114-123">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
