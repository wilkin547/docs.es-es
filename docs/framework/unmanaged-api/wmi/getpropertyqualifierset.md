---
title: Función GetPropertyQualifierSet (referencia de la API no administrada)
description: La función GetPropertyQualifierSet recupera el calificador establecido para una propiedad.
ms.date: 11/06/2017
api_name:
- GetPropertyQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyQualifierSet
helpviewer_keywords:
- GetPropertyQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b7bce241d10051e4c6be94cdfa40de23773fb0bb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798471"
---
# <a name="getpropertyqualifierset-function"></a><span data-ttu-id="fc8d6-103">GetPropertyQualifierSet función)</span><span class="sxs-lookup"><span data-stu-id="fc8d6-103">GetPropertyQualifierSet function</span></span>

<span data-ttu-id="fc8d6-104">Recupera el calificador establecido para una propiedad específica.</span><span class="sxs-lookup"><span data-stu-id="fc8d6-104">Retrieves the qualifier set for a particular property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="fc8d6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fc8d6-105">Syntax</span></span>

```cpp
HRESULT GetPropertyQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszProperty,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a><span data-ttu-id="fc8d6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fc8d6-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="fc8d6-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="fc8d6-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="fc8d6-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="fc8d6-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`\
<span data-ttu-id="fc8d6-109">de Nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="fc8d6-109">[in] The property  name.</span></span> <span data-ttu-id="fc8d6-110">`wszProperty`debe apuntar a un `LPCWSTR`válido.</span><span class="sxs-lookup"><span data-stu-id="fc8d6-110">`wszProperty` must point to a valid `LPCWSTR`.</span></span>

`ppQualSet`\
<span data-ttu-id="fc8d6-111">enuncia Recibe el puntero de interfaz que permite el acceso a los calificadores de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="fc8d6-111">[out] Receives the interface pointer that allows access to the qualifiers of the property.</span></span> <span data-ttu-id="fc8d6-112">El valor de `ppQualSet` no puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="fc8d6-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="fc8d6-113">Si se produce un error, no se devuelve un nuevo objeto y el puntero se establece en apuntar `null`a.</span><span class="sxs-lookup"><span data-stu-id="fc8d6-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="fc8d6-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fc8d6-114">Return value</span></span>

<span data-ttu-id="fc8d6-115">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="fc8d6-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fc8d6-116">Constante</span><span class="sxs-lookup"><span data-stu-id="fc8d6-116">Constant</span></span>  |<span data-ttu-id="fc8d6-117">Valor</span><span class="sxs-lookup"><span data-stu-id="fc8d6-117">Value</span></span>  |<span data-ttu-id="fc8d6-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="fc8d6-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="fc8d6-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="fc8d6-119">0x80041001</span></span> | <span data-ttu-id="fc8d6-120">Se ha producido un error general.</span><span class="sxs-lookup"><span data-stu-id="fc8d6-120">There has been a general failure.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="fc8d6-121">0x80041002</span><span class="sxs-lookup"><span data-stu-id="fc8d6-121">0x80041002</span></span> | <span data-ttu-id="fc8d6-122">El método especificado no existe.</span><span class="sxs-lookup"><span data-stu-id="fc8d6-122">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="fc8d6-123">0x80041006</span><span class="sxs-lookup"><span data-stu-id="fc8d6-123">0x80041006</span></span> | <span data-ttu-id="fc8d6-124">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="fc8d6-124">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="fc8d6-125">0x80041008</span><span class="sxs-lookup"><span data-stu-id="fc8d6-125">0x80041008</span></span> | <span data-ttu-id="fc8d6-126">Un parámetro es `null`.</span><span class="sxs-lookup"><span data-stu-id="fc8d6-126">A parameter is `null`.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | <span data-ttu-id="fc8d6-127">0x80041030</span><span class="sxs-lookup"><span data-stu-id="fc8d6-127">0x80041030</span></span> | <span data-ttu-id="fc8d6-128">La función intenta obtener los calificadores de una propiedad del sistema.</span><span class="sxs-lookup"><span data-stu-id="fc8d6-128">The function attempts to get qualifiers of a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="fc8d6-129">0</span><span class="sxs-lookup"><span data-stu-id="fc8d6-129">0</span></span> | <span data-ttu-id="fc8d6-130">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="fc8d6-130">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="fc8d6-131">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fc8d6-131">Remarks</span></span>

<span data-ttu-id="fc8d6-132">Esta función contiene una llamada al método [IWbemClassObject:: GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="fc8d6-132">This function wraps a call to the [IWbemClassObject::GetPropertyQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyqualifierset) method.</span></span>

<span data-ttu-id="fc8d6-133">Solo se admite una llamada a esta función si el objeto actual es una definición de clase CIM.</span><span class="sxs-lookup"><span data-stu-id="fc8d6-133">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="fc8d6-134">La manipulación de métodos no está disponible para los punteros [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que señalan a las instancias CIM.</span><span class="sxs-lookup"><span data-stu-id="fc8d6-134">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="fc8d6-135">Dado que cada método puede tener sus propios calificadores, el [puntero IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) permite al llamador agregar, editar o eliminar estos calificadores.</span><span class="sxs-lookup"><span data-stu-id="fc8d6-135">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

<span data-ttu-id="fc8d6-136">Dado que las propiedades del sistema no tienen calificadores, `WBEM_E_SYSTEM_PROPERTY` la función devuelve si intenta obtener un puntero [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) para una propiedad del sistema.</span><span class="sxs-lookup"><span data-stu-id="fc8d6-136">Because system properties have no qualifiers, the function returns `WBEM_E_SYSTEM_PROPERTY` if you attempt to obtain a [IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) pointer for a system property.</span></span>

## <a name="requirements"></a><span data-ttu-id="fc8d6-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fc8d6-137">Requirements</span></span>

<span data-ttu-id="fc8d6-138">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fc8d6-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="fc8d6-139">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fc8d6-139">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="fc8d6-140">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fc8d6-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="fc8d6-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="fc8d6-141">See also</span></span>

- [<span data-ttu-id="fc8d6-142">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="fc8d6-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
