---
title: Función EndEnumeration (referencia de la API no administrada)
description: La función EndEnumeration finaliza una enumeración.
ms.date: 11/06/2017
api_name:
- EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndEnumeration
helpviewer_keywords:
- EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0065dcd25430e102b965d5598c7e9a04c7857eb3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798816"
---
# <a name="endenumeration-function"></a><span data-ttu-id="fd8ee-103">Función EndEnumeration</span><span class="sxs-lookup"><span data-stu-id="fd8ee-103">EndEnumeration function</span></span>

<span data-ttu-id="fd8ee-104">Finaliza una secuencia de enumeración iniciada con una llamada a la [función BeginEnumeration](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="fd8ee-104">Terminates an enumeration sequence started with a call to the [BeginEnumeration function](beginenumeration.md).</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="fd8ee-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fd8ee-105">Syntax</span></span>

```cpp
HRESULT EndEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```

## <a name="parameters"></a><span data-ttu-id="fd8ee-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fd8ee-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="fd8ee-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="fd8ee-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="fd8ee-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="fd8ee-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="fd8ee-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fd8ee-109">Return value</span></span>

<span data-ttu-id="fd8ee-110">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="fd8ee-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fd8ee-111">Constante</span><span class="sxs-lookup"><span data-stu-id="fd8ee-111">Constant</span></span>  |<span data-ttu-id="fd8ee-112">Valor</span><span class="sxs-lookup"><span data-stu-id="fd8ee-112">Value</span></span>  |<span data-ttu-id="fd8ee-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fd8ee-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="fd8ee-114">0x80041001</span><span class="sxs-lookup"><span data-stu-id="fd8ee-114">0x80041001</span></span> | <span data-ttu-id="fd8ee-115">Se ha producido un error general.</span><span class="sxs-lookup"><span data-stu-id="fd8ee-115">There has been a general failure.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="fd8ee-116">0</span><span class="sxs-lookup"><span data-stu-id="fd8ee-116">0</span></span> | <span data-ttu-id="fd8ee-117">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="fd8ee-117">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="fd8ee-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fd8ee-118">Remarks</span></span>

<span data-ttu-id="fd8ee-119">Esta función contiene una llamada al método [IWbemClassObject:: EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="fd8ee-119">This function wraps a call to the [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="fd8ee-120">No se requiere una `EndEnumeration` llamada a la función, pero se recomienda porque libera los recursos asociados a la enumeración.</span><span class="sxs-lookup"><span data-stu-id="fd8ee-120">A call to the `EndEnumeration` function is not required, but it is recommended because it releases resources associated with the enumeration.</span></span> <span data-ttu-id="fd8ee-121">Sin embargo, los recursos se desasignan automáticamente cuando se inicia la siguiente enumeración o se libera el objeto.</span><span class="sxs-lookup"><span data-stu-id="fd8ee-121">However, the resources are deallocated automatically when the next enumeration is started or the object is released.</span></span>

## <a name="requirements"></a><span data-ttu-id="fd8ee-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fd8ee-122">Requirements</span></span>

<span data-ttu-id="fd8ee-123">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fd8ee-123">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="fd8ee-124">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fd8ee-124">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="fd8ee-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fd8ee-125">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="fd8ee-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="fd8ee-126">See also</span></span>

- [<span data-ttu-id="fd8ee-127">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="fd8ee-127">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
