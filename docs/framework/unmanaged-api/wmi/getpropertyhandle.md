---
title: Función GetPropertyHandle (referencia de API no administrada)
description: La función GetPropertyHandle devuelve un identificador único que una propiedad de identidades.
ms.date: 11/06/2017
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 103e81dfa0e455157cfce5914b711347b15b578d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460588"
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="81def-103">GetPropertyHandle (función)</span><span class="sxs-lookup"><span data-stu-id="81def-103">GetPropertyHandle function</span></span>
<span data-ttu-id="81def-104">Devuelve un identificador único que identifica una propiedad.</span><span class="sxs-lookup"><span data-stu-id="81def-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="81def-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="81def-105">Syntax</span></span>  
  
```  
HRESULT GetPropertyHandle (
   [in] int                  vFunc, 
   [in] IWbemObjectAccess*   ptr, 
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
); 
```  

## <a name="parameters"></a><span data-ttu-id="81def-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="81def-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="81def-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="81def-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="81def-108">[in] Un puntero a un [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="81def-108">[in] A pointer to an [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) instance.</span></span>

`wszPropertyName`  
<span data-ttu-id="81def-109">[in] Una cadena terminada en null de characaters codificados en UTF16 que contiene el nombre de propiedad.</span><span class="sxs-lookup"><span data-stu-id="81def-109">[in] A null-terminated string of UTF16-encoded characaters that contains the property name.</span></span>   

`pType`  
<span data-ttu-id="81def-110">[out] Un puntero a un [ `CIMTYPE` ](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) miembro de enumeración que representa el tipo CIM de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="81def-110">[out] A pointer to a [`CIMTYPE`](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`   
<span data-ttu-id="81def-111">[out] Un puntero a un entero que contiene el identificador de propiedad.</span><span class="sxs-lookup"><span data-stu-id="81def-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="81def-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="81def-112">Return value</span></span>

<span data-ttu-id="81def-113">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="81def-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="81def-114">Constante</span><span class="sxs-lookup"><span data-stu-id="81def-114">Constant</span></span>  |<span data-ttu-id="81def-115">Valor</span><span class="sxs-lookup"><span data-stu-id="81def-115">Value</span></span>  |<span data-ttu-id="81def-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="81def-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="81def-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="81def-117">0x80041002</span></span> | <span data-ttu-id="81def-118">No se encontró el nombre de propiedad especificado.</span><span class="sxs-lookup"><span data-stu-id="81def-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="81def-119">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="81def-119">0x80041008</span></span> | <span data-ttu-id="81def-120">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="81def-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="81def-121">0x8004100C</span><span class="sxs-lookup"><span data-stu-id="81def-121">0x8004100c</span></span> | <span data-ttu-id="81def-122">La propiedad solicitada es de tipo son `CIM_OBJECT` o `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="81def-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="81def-123">0</span><span class="sxs-lookup"><span data-stu-id="81def-123">0</span></span> | <span data-ttu-id="81def-124">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="81def-124">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="81def-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="81def-125">Remarks</span></span>

<span data-ttu-id="81def-126">Esta función contiene una llamada a la [IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="81def-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](https://msdn.microsoft.com/library/aa391771(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="81def-127">Puede utilizar este identificador para identificar las propiedades cuando se usa [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) métodos para leer o escribir valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="81def-127">You can use this handle to identify properties when using  [IWbemObjectAccess](https://msdn.microsoft.com/library/aa391770(v=vs.85).aspx) methods to read or write property values.</span></span>

<span data-ttu-id="81def-128">Pueden obtenerse identificadores para las propiedades de todos los tipos de datos distinto de `CIM_OBJECT` y `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="81def-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="81def-129">Devuelve el trabajo de identificadores en todas las instancias de una clase.</span><span class="sxs-lookup"><span data-stu-id="81def-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="81def-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="81def-130">Requirements</span></span>  
<span data-ttu-id="81def-131">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="81def-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="81def-132">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="81def-132">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="81def-133">**Versiones de .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="81def-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="81def-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="81def-134">See also</span></span>  
[<span data-ttu-id="81def-135">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="81def-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
