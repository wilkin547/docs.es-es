---
title: Función WritePropertyValue (referencia de API no administrada)
description: La función WritePropertyValue escribe bytes en una propiedad.
ms.date: 11/06/2017
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
ms.openlocfilehash: f2a4eb444967390492be33b25866de8a93a1698c
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/01/2018
ms.locfileid: "43393912"
---
# <a name="writepropertyvalue-function"></a><span data-ttu-id="b74df-103">Función WritePropertyValue</span><span class="sxs-lookup"><span data-stu-id="b74df-103">WritePropertyValue function</span></span>
<span data-ttu-id="b74df-104">Escribe un número especificado de bytes en una propiedad identificada por un identificador de propiedad.</span><span class="sxs-lookup"><span data-stu-id="b74df-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="b74df-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b74df-105">Syntax</span></span>  
  
```  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a><span data-ttu-id="b74df-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b74df-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b74df-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="b74df-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b74df-108">[in] Un puntero a un [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instancia.</span><span class="sxs-lookup"><span data-stu-id="b74df-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`lHandle`  
<span data-ttu-id="b74df-109">[in] Un entero que contiene el identificador que identifica esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="b74df-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="b74df-110">El identificador se puede recuperar mediante una llamada a la [GetPropertyHandle](getpropertyhandle.md) función.</span><span class="sxs-lookup"><span data-stu-id="b74df-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>   

`lNumBytes`  
<span data-ttu-id="b74df-111">[in] El número de bytes que se va a escribir en la propiedad.</span><span class="sxs-lookup"><span data-stu-id="b74df-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="b74df-112">Consulte la [comentarios](#remarks) sección para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="b74df-112">See the [Remarks](#remarks) section for more information.</span></span>

`pHandle`   
<span data-ttu-id="b74df-113">[out] Un puntero a la matriz de bytes que contiene los datos.</span><span class="sxs-lookup"><span data-stu-id="b74df-113">[out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="b74df-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b74df-114">Return value</span></span>

<span data-ttu-id="b74df-115">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="b74df-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b74df-116">Constante</span><span class="sxs-lookup"><span data-stu-id="b74df-116">Constant</span></span>  |<span data-ttu-id="b74df-117">Valor</span><span class="sxs-lookup"><span data-stu-id="b74df-117">Value</span></span>  |<span data-ttu-id="b74df-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="b74df-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="b74df-119">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="b74df-119">0x80041008</span></span> | <span data-ttu-id="b74df-120">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="b74df-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="b74df-121">0 x 80041005.</span><span class="sxs-lookup"><span data-stu-id="b74df-121">0x80041005</span></span> | <span data-ttu-id="b74df-122">Se ha producido un error de coincidencia de tipo.</span><span class="sxs-lookup"><span data-stu-id="b74df-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b74df-123">0</span><span class="sxs-lookup"><span data-stu-id="b74df-123">0</span></span> | <span data-ttu-id="b74df-124">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="b74df-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="b74df-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="b74df-125">Remarks</span></span>

<span data-ttu-id="b74df-126">Esta función contiene una llamada a la [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) método.</span><span class="sxs-lookup"><span data-stu-id="b74df-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) method.</span></span>

<span data-ttu-id="b74df-127">Use esta función para establecer la cadena y todos los otros que no sean de`DWORD` o que no sean-`QWORD` datos.</span><span class="sxs-lookup"><span data-stu-id="b74df-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="b74df-128">Para los valores de propiedad, `lNumBytes` debe ser el tamaño de datos correcto del tipo de propiedad especificado.</span><span class="sxs-lookup"><span data-stu-id="b74df-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="b74df-129">Para los valores de propiedad de cadena, `lNumBytes` debe ser la longitud de la cadena especificada en bytes y la cadena debe tener una longitud en bytes incluso y seguir con un carácter de terminación null.</span><span class="sxs-lookup"><span data-stu-id="b74df-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="b74df-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b74df-130">Requirements</span></span>  
<span data-ttu-id="b74df-131">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b74df-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b74df-132">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b74df-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b74df-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b74df-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b74df-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="b74df-134">See also</span></span>  
[<span data-ttu-id="b74df-135">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="b74df-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
