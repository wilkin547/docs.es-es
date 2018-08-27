---
title: GetPropertyOrigin (función) (referencia de API Unmnaged)
description: GetPropertyOrigin (función) determina la clase en el que se declara una propiedad.
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
ms.openlocfilehash: 86c512f25c40f201d818b6789c6410bfb095b878
ms.sourcegitcommit: e614e0f3b031293e4107f37f752be43652f3f253
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/26/2018
ms.locfileid: "42933522"
---
# <a name="getpropertyorigin-function"></a><span data-ttu-id="e1eb6-103">GetPropertyOrigin (función)</span><span class="sxs-lookup"><span data-stu-id="e1eb6-103">GetPropertyOrigin function</span></span>
<span data-ttu-id="e1eb6-104">Determina la clase en el que se declara una propiedad.</span><span class="sxs-lookup"><span data-stu-id="e1eb6-104">Determines the class in which a property is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="e1eb6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e1eb6-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="e1eb6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e1eb6-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e1eb6-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="e1eb6-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e1eb6-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="e1eb6-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="e1eb6-109">[in] El nombre de la propiedad del objeto cuya clase propietaria se solicita.</span><span class="sxs-lookup"><span data-stu-id="e1eb6-109">[in] The name of the property for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="e1eb6-110">[out] Recibe el nombre de la clase que posee la propiedad.</span><span class="sxs-lookup"><span data-stu-id="e1eb6-110">[out] Receives the name of the class that owns the property.</span></span>

## <a name="return-value"></a><span data-ttu-id="e1eb6-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e1eb6-111">Return value</span></span>

<span data-ttu-id="e1eb6-112">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="e1eb6-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e1eb6-113">Constante</span><span class="sxs-lookup"><span data-stu-id="e1eb6-113">Constant</span></span>  |<span data-ttu-id="e1eb6-114">Valor</span><span class="sxs-lookup"><span data-stu-id="e1eb6-114">Value</span></span>  |<span data-ttu-id="e1eb6-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="e1eb6-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="e1eb6-116">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="e1eb6-116">0x80041001</span></span> | <span data-ttu-id="e1eb6-117">Ha habido un error general.</span><span class="sxs-lookup"><span data-stu-id="e1eb6-117">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="e1eb6-118">0x80041002</span><span class="sxs-lookup"><span data-stu-id="e1eb6-118">0x80041002</span></span> | <span data-ttu-id="e1eb6-119">No se encontró la propiedad especificada.</span><span class="sxs-lookup"><span data-stu-id="e1eb6-119">The specified property was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e1eb6-120">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="e1eb6-120">0x80041008</span></span> | <span data-ttu-id="e1eb6-121">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="e1eb6-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e1eb6-122">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="e1eb6-122">0x80041006</span></span> | <span data-ttu-id="e1eb6-123">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="e1eb6-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e1eb6-124">0</span><span class="sxs-lookup"><span data-stu-id="e1eb6-124">0</span></span> | <span data-ttu-id="e1eb6-125">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="e1eb6-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e1eb6-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e1eb6-126">Remarks</span></span>

<span data-ttu-id="e1eb6-127">Esta función contiene una llamada a la [IWbemClassObject::GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) método.</span><span class="sxs-lookup"><span data-stu-id="e1eb6-127">This function wraps a call to the [IWbemClassObject::GetPropertyOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getpropertyorigin) method.</span></span>

<span data-ttu-id="e1eb6-128">Porque una clase puede heredar propiedades de una o más clases bases, los desarrolladores a menudo desean determinar la propiedad en el que se define un método determinado.</span><span class="sxs-lookup"><span data-stu-id="e1eb6-128">Because a class can inherit properties from one or more base classes, developers often want to determine the property in which a given method is defined.</span></span>

<span data-ttu-id="e1eb6-129">El `pstrClassName` parámetro no debe apuntar a una `BSTR` antes de llama a la función porque se trata de un `out` parámetro; este puntero no se desasigna cuando la función vuelve.</span><span class="sxs-lookup"><span data-stu-id="e1eb6-129">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="e1eb6-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e1eb6-130">Requirements</span></span>  
<span data-ttu-id="e1eb6-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e1eb6-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e1eb6-132">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="e1eb6-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e1eb6-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e1eb6-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e1eb6-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="e1eb6-134">See also</span></span>  
[<span data-ttu-id="e1eb6-135">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="e1eb6-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
