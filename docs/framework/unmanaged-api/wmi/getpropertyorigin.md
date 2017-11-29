---
title: "Función GetPropertyOrigin (referencia de la API de Unmnaged)"
description: "La función GetPropertyOrigin determina la clase en la que se declara una propiedad."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: GetPropertyOrigin
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: GetPropertyOrigin
helpviewer_keywords: GetPropertyOrigin function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 68df29e88b41cb12d002913d5bbd42050395d871
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="getpropertyorigin-function"></a><span data-ttu-id="75c08-103">GetPropertyOrigin (función)</span><span class="sxs-lookup"><span data-stu-id="75c08-103">GetPropertyOrigin function</span></span>
<span data-ttu-id="75c08-104">Determina la clase en la que se declara una propiedad.</span><span class="sxs-lookup"><span data-stu-id="75c08-104">Determines the class in which a property is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="75c08-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="75c08-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="75c08-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="75c08-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="75c08-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="75c08-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="75c08-108">[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="75c08-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="75c08-109">[in] El nombre de la propiedad para el objeto cuya clase propietaria se solicita.</span><span class="sxs-lookup"><span data-stu-id="75c08-109">[in] The name of the property for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="75c08-110">[out] Recibe el nombre de la clase que posee la propiedad.</span><span class="sxs-lookup"><span data-stu-id="75c08-110">[out] Receives the name of the class that owns the property.</span></span>

## <a name="return-value"></a><span data-ttu-id="75c08-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="75c08-111">Return value</span></span>

<span data-ttu-id="75c08-112">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="75c08-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="75c08-113">Constante</span><span class="sxs-lookup"><span data-stu-id="75c08-113">Constant</span></span>  |<span data-ttu-id="75c08-114">Valor</span><span class="sxs-lookup"><span data-stu-id="75c08-114">Value</span></span>  |<span data-ttu-id="75c08-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="75c08-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="75c08-116">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="75c08-116">0x80041001</span></span> | <span data-ttu-id="75c08-117">Ha habido un error general.</span><span class="sxs-lookup"><span data-stu-id="75c08-117">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="75c08-118">0x80041002</span><span class="sxs-lookup"><span data-stu-id="75c08-118">0x80041002</span></span> | <span data-ttu-id="75c08-119">No se encontró la propiedad especificada.</span><span class="sxs-lookup"><span data-stu-id="75c08-119">The specified property was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="75c08-120">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="75c08-120">0x80041008</span></span> | <span data-ttu-id="75c08-121">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="75c08-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="75c08-122">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="75c08-122">0x80041006</span></span> | <span data-ttu-id="75c08-123">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="75c08-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="75c08-124">0</span><span class="sxs-lookup"><span data-stu-id="75c08-124">0</span></span> | <span data-ttu-id="75c08-125">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="75c08-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="75c08-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="75c08-126">Remarks</span></span>

<span data-ttu-id="75c08-127">Esta función contiene una llamada a la [IWbemClassObject::GetPropertyOrigin](https://msdn.microsoft.com/library/aa391449(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="75c08-127">This function wraps a call to the [IWbemClassObject::GetPropertyOrigin](https://msdn.microsoft.com/library/aa391449(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="75c08-128">Dado que una clase puede heredar propiedades de una o más clases base, los programadores a menudo desean determinar la propiedad en el que se define un método determinado.</span><span class="sxs-lookup"><span data-stu-id="75c08-128">Because a class can inherit properties from one or more base classes, developers often want to determine the property in which a given method is defined.</span></span>

<span data-ttu-id="75c08-129">El `pstrClassName` parámetro no debe apuntar a válido `BSTR` antes de llama a la función porque se trata de un `out` parámetro; en este puntero no se cancela la asignación después de la función devuelve.</span><span class="sxs-lookup"><span data-stu-id="75c08-129">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="75c08-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="75c08-130">Requirements</span></span>  
<span data-ttu-id="75c08-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="75c08-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="75c08-132">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="75c08-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="75c08-133">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="75c08-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="75c08-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="75c08-134">See also</span></span>  
[<span data-ttu-id="75c08-135">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="75c08-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
