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
ms.openlocfilehash: e4c44379d9db0f5e98f3ca66ec0486961ec2df3a
ms.sourcegitcommit: 046a9c22487551360e20ec39fc21eef99820a254
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/14/2020
ms.locfileid: "83396946"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="e266d-102">ISOSDacInterface:: GetMethodDescData (método)</span><span class="sxs-lookup"><span data-stu-id="e266d-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="e266d-103">Obtiene los datos para el puntero de MethodDesc dado.</span><span class="sxs-lookup"><span data-stu-id="e266d-103">Gets the data for the given MethodDesc pointer.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="e266d-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e266d-104">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="e266d-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e266d-105">Parameters</span></span>

`methodDesc`\
<span data-ttu-id="e266d-106">de Dirección de la MethodDesc.</span><span class="sxs-lookup"><span data-stu-id="e266d-106">[in] The address of the MethodDesc.</span></span>

`ip`\
<span data-ttu-id="e266d-107">de Dirección IP del método.</span><span class="sxs-lookup"><span data-stu-id="e266d-107">[in] The IP address of the method.</span></span>

`data`\
<span data-ttu-id="e266d-108">enuncia Los datos asociados al MethodDesc tal y como se devuelven desde las API internas.</span><span class="sxs-lookup"><span data-stu-id="e266d-108">[out] The data associated with the MethodDesc as returned from the internal APIs.</span></span>

`cRevertedRejitVersions`\
<span data-ttu-id="e266d-109">enuncia Número de versiones revertidas de rejit.</span><span class="sxs-lookup"><span data-stu-id="e266d-109">[out] The number of reverted rejit versions.</span></span>

`rgRevertedRejitData`\
<span data-ttu-id="e266d-110">enuncia Los datos asociados a las versiones revertidas de rejit devueltas por las API internas.</span><span class="sxs-lookup"><span data-stu-id="e266d-110">[out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span>

`pcNeededRevertedRejitData`\
<span data-ttu-id="e266d-111">enuncia El número de bytes necesarios para almacenar los datos asociados a las versiones revertidas de ReJit.</span><span class="sxs-lookup"><span data-stu-id="e266d-111">[out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="e266d-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e266d-112">Remarks</span></span>

<span data-ttu-id="e266d-113">El método proporcionado forma parte de la `ISOSDacInterface` interfaz y corresponde a la ranura 21 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="e266d-113">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 21st slot of the virtual method table.</span></span> <span data-ttu-id="e266d-114">Para poder utilizarlos, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) debe definirse como un entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="e266d-114">To be able to use them, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) must be defined as a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="e266d-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e266d-115">Requirements</span></span>

<span data-ttu-id="e266d-116">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e266d-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="e266d-117">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e266d-117">**Header:** None</span></span>  
<span data-ttu-id="e266d-118">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="e266d-118">**Library:** None</span></span>  
<span data-ttu-id="e266d-119">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e266d-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="e266d-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="e266d-120">See also</span></span>

- [<span data-ttu-id="e266d-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="e266d-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="e266d-122">Interfaz ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="e266d-122">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)
