---
title: Función WritePropertyValue (referencia de la API no administrada)
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
ms.openlocfilehash: f02fb3877d55e9f47384b281573202712c29c606
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73107291"
---
# <a name="writepropertyvalue-function"></a><span data-ttu-id="9195d-103">WritePropertyValue función)</span><span class="sxs-lookup"><span data-stu-id="9195d-103">WritePropertyValue function</span></span>
<span data-ttu-id="9195d-104">Escribe un número específico de bytes en una propiedad identificada por un controlador de propiedad.</span><span class="sxs-lookup"><span data-stu-id="9195d-104">Writes a specified number of bytes to a property identified by a property handle.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="9195d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="9195d-105">Syntax</span></span>  
  
```cpp  
HRESULT WritePropertyValue (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] long                 lHandle,
   [in] long                 lNumBytes,
   [in] byte*                aData
); 
```  

## <a name="parameters"></a><span data-ttu-id="9195d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="9195d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="9195d-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="9195d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="9195d-108">de Puntero a una instancia de [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) .</span><span class="sxs-lookup"><span data-stu-id="9195d-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`lHandle`  
<span data-ttu-id="9195d-109">de Entero que contiene el identificador que identifica esta propiedad.</span><span class="sxs-lookup"><span data-stu-id="9195d-109">[in] An integer that contains the handle that identifies this property.</span></span> <span data-ttu-id="9195d-110">El identificador se puede recuperar llamando a la función [GetPropertyHandle](getpropertyhandle.md) .</span><span class="sxs-lookup"><span data-stu-id="9195d-110">The handle can be retrieved by calling the [GetPropertyHandle](getpropertyhandle.md) function.</span></span>   

`lNumBytes`  
<span data-ttu-id="9195d-111">de Número de bytes que se escriben en la propiedad.</span><span class="sxs-lookup"><span data-stu-id="9195d-111">[in] The number of bytes being written to the property.</span></span> <span data-ttu-id="9195d-112">Vea la sección [comentarios](#remarks) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="9195d-112">See the [Remarks](#remarks) section for more information.</span></span>

`pHandle`   
<span data-ttu-id="9195d-113">enuncia Puntero a la matriz de bytes que contiene los datos.</span><span class="sxs-lookup"><span data-stu-id="9195d-113">[out] A pointer to the byte array that contains the data.</span></span>

## <a name="return-value"></a><span data-ttu-id="9195d-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="9195d-114">Return value</span></span>

<span data-ttu-id="9195d-115">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="9195d-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="9195d-116">Constante</span><span class="sxs-lookup"><span data-stu-id="9195d-116">Constant</span></span>  |<span data-ttu-id="9195d-117">Valor</span><span class="sxs-lookup"><span data-stu-id="9195d-117">Value</span></span>  |<span data-ttu-id="9195d-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="9195d-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="9195d-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="9195d-119">0x80041008</span></span> | <span data-ttu-id="9195d-120">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="9195d-120">A parameter is not valid.</span></span> |
|`WBEM_E_TYPE_MISMATCH` | <span data-ttu-id="9195d-121">0x80041005</span><span class="sxs-lookup"><span data-stu-id="9195d-121">0x80041005</span></span> | <span data-ttu-id="9195d-122">Error de coincidencia de tipos.</span><span class="sxs-lookup"><span data-stu-id="9195d-122">A type mismatch occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="9195d-123">0</span><span class="sxs-lookup"><span data-stu-id="9195d-123">0</span></span> | <span data-ttu-id="9195d-124">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="9195d-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="9195d-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="9195d-125">Remarks</span></span>

<span data-ttu-id="9195d-126">Esta función contiene una llamada al método [IWbemClassObject:: WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) .</span><span class="sxs-lookup"><span data-stu-id="9195d-126">This function wraps a call to the [IWbemClassObject::WritePropertyValue](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-writepropertyvalue) method.</span></span>

<span data-ttu-id="9195d-127">Utilice esta función para establecer la cadena y todos los demás datos no`DWORD` o no`QWORD`.</span><span class="sxs-lookup"><span data-stu-id="9195d-127">Use this function to set string and all other non-`DWORD` or non-`QWORD` data.</span></span>

<span data-ttu-id="9195d-128">Para los valores de propiedad que no son de cadena, `lNumBytes` debe ser el tamaño de datos correcto del tipo de propiedad especificado.</span><span class="sxs-lookup"><span data-stu-id="9195d-128">For nonstring property values, `lNumBytes` must be the correct data size of the property type specified.</span></span> <span data-ttu-id="9195d-129">En el caso de los valores de propiedad de cadena, `lNumBytes` debe ser la longitud de la cadena especificada en bytes y la propia cadena debe tener una longitud uniforme en bytes y seguirse con un carácter de terminación null.</span><span class="sxs-lookup"><span data-stu-id="9195d-129">For string property values, `lNumBytes` must be the length of the specified string in bytes, and the string itself must be of an even length in bytes and be followed with a null-termination character.</span></span>

## <a name="requirements"></a><span data-ttu-id="9195d-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="9195d-130">Requirements</span></span>  
<span data-ttu-id="9195d-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="9195d-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9195d-132">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="9195d-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="9195d-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="9195d-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9195d-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="9195d-134">See also</span></span>

- [<span data-ttu-id="9195d-135">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="9195d-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
