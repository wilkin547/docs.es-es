---
title: Función GetPropertyOrigin (referencia de la API no administrada)
description: La función GetPropertyOrigin determina la clase en la que se declara una propiedad.
ms.date: 11/06/2017
api_name:
- GetPropertyOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyOrigin
helpviewer_keywords:
- GetPropertyOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0c2d0f23f3dd2d52f73f09c32d4e3118a9ed5ea3
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798491"
---
# <a name="getpropertyorigin-function"></a><span data-ttu-id="fc966-103">Función GetPropertyOrigin</span><span class="sxs-lookup"><span data-stu-id="fc966-103">GetPropertyOrigin function</span></span>

<span data-ttu-id="fc966-104">Determina la clase en la que se declara una propiedad.</span><span class="sxs-lookup"><span data-stu-id="fc966-104">Determines the class in which a property is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="fc966-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc966-105">Syntax</span></span>

```cpp
HRESULT GetPropertyOrigin (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
);
```

## <a name="parameters"></a><span data-ttu-id="fc966-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fc966-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="fc966-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="fc966-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="fc966-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="fc966-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`\
<span data-ttu-id="fc966-109">de Nombre de la propiedad para el objeto cuya clase propietaria se está solicitando.</span><span class="sxs-lookup"><span data-stu-id="fc966-109">[in] The name of the property for the object whose owning class is being requested.</span></span>

`pstrClassName`\
<span data-ttu-id="fc966-110">enuncia Recibe el nombre de la clase a la que pertenece la propiedad.</span><span class="sxs-lookup"><span data-stu-id="fc966-110">[out] Receives the name of the class that owns the property.</span></span>

## <a name="return-value"></a><span data-ttu-id="fc966-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fc966-111">Return value</span></span>

<span data-ttu-id="fc966-112">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="fc966-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fc966-113">Constante</span><span class="sxs-lookup"><span data-stu-id="fc966-113">Constant</span></span>  |<span data-ttu-id="fc966-114">Valor</span><span class="sxs-lookup"><span data-stu-id="fc966-114">Value</span></span>  |<span data-ttu-id="fc966-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fc966-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="fc966-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="fc966-116">0x80041001</span></span> | <span data-ttu-id="fc966-117">Se ha producido un error general.</span><span class="sxs-lookup"><span data-stu-id="fc966-117">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="fc966-118">0x80041002</span><span class="sxs-lookup"><span data-stu-id="fc966-118">0x80041002</span></span> | <span data-ttu-id="fc966-119">No se encontró la propiedad especificada.</span><span class="sxs-lookup"><span data-stu-id="fc966-119">The specified property was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="fc966-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="fc966-120">0x80041008</span></span> | <span data-ttu-id="fc966-121">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="fc966-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="fc966-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="fc966-122">0x80041006</span></span> | <span data-ttu-id="fc966-123">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="fc966-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="fc966-124">0</span><span class="sxs-lookup"><span data-stu-id="fc966-124">0</span></span> | <span data-ttu-id="fc966-125">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="fc966-125">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="fc966-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc966-126">Remarks</span></span>

<span data-ttu-id="fc966-127">Esta función contiene una llamada al método [IWbemClassObject:: GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) .</span><span class="sxs-lookup"><span data-stu-id="fc966-127">This function wraps a call to the [IWbemClassObject::GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) method.</span></span>

<span data-ttu-id="fc966-128">Dado que una clase puede heredar propiedades de una o varias clases base, los desarrolladores suelen querer determinar la propiedad en la que se define un método determinado.</span><span class="sxs-lookup"><span data-stu-id="fc966-128">Because a class can inherit properties from one or more base classes, developers often want to determine the property in which a given method is defined.</span></span>

<span data-ttu-id="fc966-129">El `pstrClassName` parámetro no debe señalar a un válido `BSTR` antes de que se llame a la función porque `out` es un parámetro; este puntero no se desasigna después de que la función devuelva un error.</span><span class="sxs-lookup"><span data-stu-id="fc966-129">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="fc966-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc966-130">Requirements</span></span>

<span data-ttu-id="fc966-131">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc966-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="fc966-132">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fc966-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="fc966-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fc966-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="fc966-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc966-134">See also</span></span>

- [<span data-ttu-id="fc966-135">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="fc966-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
