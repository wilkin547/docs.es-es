---
title: 'IXCLRDataProcess:: GetRuntimeNameByAddress (método)'
ms.date: 4/27/2020
api.name:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method
helpviewer.keywords:
- IXCLRDataProcess::GetRuntimeNameByAddress Method [.NET Framework debugging]
topic_type:
- apiref
author: tommcdon
ms.author: tommcdon
ms.openlocfilehash: 6648bdafe6e5cdd402bcfa02a148c57f0f1e209e
ms.sourcegitcommit: bc293b14af795e0e999e3304dd40c0222cf2ffe4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/26/2020
ms.locfileid: "96275571"
---
# <a name="ixclrdataprocessgetruntimenamebyaddress-method"></a><span data-ttu-id="0c1d3-102">IXCLRDataProcess:: GetRuntimeNameByAddress (método)</span><span class="sxs-lookup"><span data-stu-id="0c1d3-102">IXCLRDataProcess::GetRuntimeNameByAddress Method</span></span>

<span data-ttu-id="0c1d3-103">Obtiene un nombre para la dirección especificada.</span><span class="sxs-lookup"><span data-stu-id="0c1d3-103">Gets a name for the given address.</span></span>

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a><span data-ttu-id="0c1d3-104">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="0c1d3-104">Syntax</span></span>

```cpp
HRESULT GetRuntimeNameByAddress(
    [in] CLRDATA_ADDRESS address,
    [in] ULONG32 flags,
    [in] ULONG32 bufLen,
    [out] ULONG32 *nameLen,
    [out, size_is(bufLen)] WCHAR nameBuf[],
    [out] CLRDATA_ADDRESS* displacement
);
```

## <a name="parameters"></a><span data-ttu-id="0c1d3-105">Parámetros</span><span class="sxs-lookup"><span data-stu-id="0c1d3-105">Parameters</span></span>

`address`\
<span data-ttu-id="0c1d3-106">de `CLRDATA_ADDRESS` Valor que representa una dirección de código.</span><span class="sxs-lookup"><span data-stu-id="0c1d3-106">[in] A `CLRDATA_ADDRESS` value that represents a code address.</span></span>

`flags`\
<span data-ttu-id="0c1d3-107">de Establezca en ' 0 '.</span><span class="sxs-lookup"><span data-stu-id="0c1d3-107">[in] Set to '0'.</span></span>

`bufLen`\
<span data-ttu-id="0c1d3-108">de Longitud del búfer.</span><span class="sxs-lookup"><span data-stu-id="0c1d3-108">[in] The length of the buffer.</span></span>

`namLen`\
<span data-ttu-id="0c1d3-109">enuncia Puntero al número de caracteres devueltos.</span><span class="sxs-lookup"><span data-stu-id="0c1d3-109">[out] A pointer to the number of characters returned.</span></span>

`namBuf`\
<span data-ttu-id="0c1d3-110">[out, size_is ( `bufLen` )] búfer de entrada de longitud `bufLen` que almacena el nombre en tiempo de ejecución.</span><span class="sxs-lookup"><span data-stu-id="0c1d3-110">[out, size_is(`bufLen`)] The input buffer of length `bufLen` that stores the runtime name.</span></span>

`displacement`\
<span data-ttu-id="0c1d3-111">enuncia `CLRDATA_ADDRESS` Puntero al desplazamiento de código del símbolo devuelto.</span><span class="sxs-lookup"><span data-stu-id="0c1d3-111">[out] A `CLRDATA_ADDRESS` pointer to the code offset of the returned symbol.</span></span>

## <a name="remarks"></a><span data-ttu-id="0c1d3-112">Comentarios</span><span class="sxs-lookup"><span data-stu-id="0c1d3-112">Remarks</span></span>

<span data-ttu-id="0c1d3-113">El método proporcionado forma parte de la `IXCLRDataProcess` interfaz y corresponde a la ranura 16 de la tabla del método virtual.</span><span class="sxs-lookup"><span data-stu-id="0c1d3-113">The provided method is part of the `IXCLRDataProcess` interface and corresponds to the 16th slot of the virtual-method table.</span></span>

> [!NOTE]
> <span data-ttu-id="0c1d3-114">Si el búfer no es suficientemente grande para el nombre, este método devuelve `S_FALSE` y establece `nameLen` en la longitud de búfer necesaria.</span><span class="sxs-lookup"><span data-stu-id="0c1d3-114">If the buffer is not large enough for the name, this method returns `S_FALSE` and sets `nameLen` to the required buffer length.</span></span>

## <a name="requirements"></a><span data-ttu-id="0c1d3-115">Requisitos</span><span class="sxs-lookup"><span data-stu-id="0c1d3-115">Requirements</span></span>

<span data-ttu-id="0c1d3-116">**Plataformas:** Consulte [los requisitos del sistema](../../get-started/system-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="0c1d3-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md)</span></span>\
<span data-ttu-id="0c1d3-117">**Encabezado:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="0c1d3-117">**Header:** None\</span></span>
<span data-ttu-id="0c1d3-118">**Biblioteca:** Ninguna</span><span class="sxs-lookup"><span data-stu-id="0c1d3-118">**Library:** None\</span></span>
<span data-ttu-id="0c1d3-119">**.NET Framework versiones:**[!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span><span class="sxs-lookup"><span data-stu-id="0c1d3-119">**.NET Framework Versions:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="0c1d3-120">Vea también</span><span class="sxs-lookup"><span data-stu-id="0c1d3-120">See also</span></span>

- [<span data-ttu-id="0c1d3-121">Depuración</span><span class="sxs-lookup"><span data-stu-id="0c1d3-121">Debugging</span></span>](index.md)
- [<span data-ttu-id="0c1d3-122">Interfaz IXCLRDataProcess</span><span class="sxs-lookup"><span data-stu-id="0c1d3-122">IXCLRDataProcess Interface</span></span>](ixclrdataprocess-interface.md)
