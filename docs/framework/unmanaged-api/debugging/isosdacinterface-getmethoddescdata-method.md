---
title: Método ISOSDacInterface::GetMethodDescData
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
ms.openlocfilehash: 4e32facc65162c4deb853cd507a00126e5f786e7
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/05/2019
ms.locfileid: "57352599"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a><span data-ttu-id="fb16e-102">Método ISOSDacInterface::GetMethodDescData</span><span class="sxs-lookup"><span data-stu-id="fb16e-102">ISOSDacInterface::GetMethodDescData Method</span></span>

<span data-ttu-id="fb16e-103">Obtiene los datos para el puntero de MethodDesc determinado.</span><span class="sxs-lookup"><span data-stu-id="fb16e-103">Gets the data for the given MethodDesc pointer.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="fb16e-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb16e-104">Syntax</span></span>

```
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

## <a name="parameters"></a><span data-ttu-id="fb16e-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fb16e-105">Parameters</span></span>

`methodDesc`\
<span data-ttu-id="fb16e-106">[in] La dirección de la MethodDesc.</span><span class="sxs-lookup"><span data-stu-id="fb16e-106">[in] The address of the MethodDesc.</span></span>

`ip`\
<span data-ttu-id="fb16e-107">[in] La dirección IP del método.</span><span class="sxs-lookup"><span data-stu-id="fb16e-107">[in] The IP address of the method.</span></span>

`data`\
<span data-ttu-id="fb16e-108">[out] Los datos asociados con el MethodDesc devuelto desde las API internas.</span><span class="sxs-lookup"><span data-stu-id="fb16e-108">[out] The data associated with the MethodDesc as returned from the internal APIs.</span></span>

`cRevertedRejitVersions`\
<span data-ttu-id="fb16e-109">[out] El número de versiones de rejit revertida.</span><span class="sxs-lookup"><span data-stu-id="fb16e-109">[out] The number of reverted rejit versions.</span></span>

`rgRevertedRejitData`\
<span data-ttu-id="fb16e-110">[out] Los datos asociados con las versiones de rejit revertida devuelto desde las API internas.</span><span class="sxs-lookup"><span data-stu-id="fb16e-110">[out] The data associated with the reverted rejit versions as returned from the internal APIs.</span></span>

`pcNeededRevertedRejitData`\
<span data-ttu-id="fb16e-111">[out] El número de bytes necesarios para almacenar los datos asociados con las versiones de ReJit revertidas.</span><span class="sxs-lookup"><span data-stu-id="fb16e-111">[out] The number of bytes required to store the data associated with the reverted ReJit versions.</span></span>

## <a name="remarks"></a><span data-ttu-id="fb16e-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fb16e-112">Remarks</span></span>

<span data-ttu-id="fb16e-113">El método proporcionado forma parte de la `ISOSDacInterface` interfaz y corresponde a la ranura de la tabla de métodos virtuales 20.</span><span class="sxs-lookup"><span data-stu-id="fb16e-113">The provided method is part of the `ISOSDacInterface` interface and corresponds to the 20th slot of the virtual method table.</span></span> <span data-ttu-id="fb16e-114">Para poder utilizarlos, [ `CLRDATA_ADDRESS` ](../common-data-types-unmanaged-api-reference.md) debe definirse como un entero de 64 bits sin signo.</span><span class="sxs-lookup"><span data-stu-id="fb16e-114">To be able to use them, [`CLRDATA_ADDRESS`](../common-data-types-unmanaged-api-reference.md) must be defined as a 64-bit unsigned integer.</span></span>

## <a name="requirements"></a><span data-ttu-id="fb16e-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb16e-115">Requirements</span></span>

<span data-ttu-id="fb16e-116">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb16e-116">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
<span data-ttu-id="fb16e-117">**Encabezado**: Ninguna</span><span class="sxs-lookup"><span data-stu-id="fb16e-117">**Header:** None</span></span>  
<span data-ttu-id="fb16e-118">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="fb16e-118">**Library:** None</span></span>  
<span data-ttu-id="fb16e-119">**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fb16e-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>  

## <a name="see-also"></a><span data-ttu-id="fb16e-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb16e-120">See also</span></span>

- [<span data-ttu-id="fb16e-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="fb16e-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="fb16e-122">Interfaz ISOSDacInterface</span><span class="sxs-lookup"><span data-stu-id="fb16e-122">ISOSDacInterface Interface</span></span>](isosdacinterface-interface.md)