---
title: "Función WritePropertyValue (referencia de API no administrada)"
description: "La función WritePropertyValue escribe bytes a una propiedad."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- WritePropertyValue
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- WritePropertyValue
helpviewer_keywords:
- WritePropertyValue function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: 7221c9e0f1cb49ab0e27130ce69c0527ba903148
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="writepropertyvalue-function"></a><span data-ttu-id="de179-103">WritePropertyValue (función)</span><span class="sxs-lookup"><span data-stu-id="de179-103">WritePropertyValue function</span></span>
<span data-ttu-id="de179-104">Escribe un número especificado de bytes en una propiedad identificada por un identificador de propiedad.</span><span class="sxs-lookup"><span data-stu-id="de179-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="de179-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="de179-105">Syntax</span></span>  
  
```  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a><span data-ttu-id="de179-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="de179-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="de179-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="de179-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="de179-108">[in] Un puntero a un [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="de179-108">[in] A pointer to an [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) instance.</span></span>

`lHandle`  
<span data-ttu-id="de179-109">[in] Un entero que contiene el identificador que identifica esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="de179-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="de179-110">El identificador se puede recuperar mediante una llamada a la [GetPropertyHandle](getpropertyhandle.md) (función).</span><span class="sxs-lookup"><span data-stu-id="de179-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>   

`lNumBytes`  
<span data-ttu-id="de179-111">[in] El número de bytes que se va a escribir en la propiedad.</span><span class="sxs-lookup"><span data-stu-id="de179-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="de179-112">Consulte la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="de179-112">See the [Remarks](#remarks) section for more information.</span></span>

`pHandle`   
<span data-ttu-id="de179-113">[out] Un puntero a la matriz de bytes que contiene los datos.</span><span class="sxs-lookup"><span data-stu-id="de179-113">[out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="de179-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="de179-114">Return value</span></span>

<span data-ttu-id="de179-115">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="de179-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="de179-116">Constante</span><span class="sxs-lookup"><span data-stu-id="de179-116">Constant</span></span>  |<span data-ttu-id="de179-117">Valor</span><span class="sxs-lookup"><span data-stu-id="de179-117">Value</span></span>  |<span data-ttu-id="de179-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="de179-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="de179-119">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="de179-119">0x80041008</span></span> | <span data-ttu-id="de179-120">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="de179-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="de179-121">0 x 80041005</span><span class="sxs-lookup"><span data-stu-id="de179-121">0x80041005</span></span> | <span data-ttu-id="de179-122">Se produjo un error de coincidencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="de179-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="de179-123">0</span><span class="sxs-lookup"><span data-stu-id="de179-123">0</span></span> | <span data-ttu-id="de179-124">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="de179-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="de179-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="de179-125">Remarks</span></span>

<span data-ttu-id="de179-126">Esta función contiene una llamada a la [IWbemClassObject::WritePropertyValue](https://msdn.microsoft.com/library/aa391783(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="de179-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](https://msdn.microsoft.com/library/aa391783(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="de179-127">Use esta función para establecer la cadena y todos los demás no -`DWORD` o no-`QWORD` datos.</span><span class="sxs-lookup"><span data-stu-id="de179-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="de179-128">Para los valores de propiedad que no son cadenas, `lNumBytes` debe ser el tamaño de los datos correctos del tipo de propiedad especificado.</span><span class="sxs-lookup"><span data-stu-id="de179-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="de179-129">Para los valores de propiedad de cadena, `lNumBytes` deben tener la longitud de la cadena especificada en bytes y la cadena debe ser de un par de longitud en bytes e ir seguida de un carácter de terminación null.</span><span class="sxs-lookup"><span data-stu-id="de179-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="de179-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="de179-130">Requirements</span></span>  
<span data-ttu-id="de179-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="de179-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de179-132">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="de179-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="de179-133">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="de179-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de179-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="de179-134">See also</span></span>  
[<span data-ttu-id="de179-135">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="de179-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
