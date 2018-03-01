---
title: "Función GetMethodOrigin (referencia de API no administrada)"
description: "La función GetMethodOrigin determina la clase en la que se declara un método."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology:
- dotnet-clr
ms.topic: reference
api_name:
- GetMethodOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodOrigin
helpviewer_keywords:
- GetMethodOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload:
- dotnet
ms.openlocfilehash: a97376b459a5d9cce9b18ff692ac4c7535a24a56
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="93aa5-103">GetMethodOrigin (función)</span><span class="sxs-lookup"><span data-stu-id="93aa5-103">GetMethodOrigin function</span></span>
<span data-ttu-id="93aa5-104">Determina la clase en la que se declara un método.</span><span class="sxs-lookup"><span data-stu-id="93aa5-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="93aa5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="93aa5-105">Syntax</span></span>  
  
```  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="93aa5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="93aa5-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="93aa5-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="93aa5-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="93aa5-108">[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="93aa5-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="93aa5-109">[in] El nombre del método para el objeto cuya clase propietaria se solicita.</span><span class="sxs-lookup"><span data-stu-id="93aa5-109">[in] The name of the method for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="93aa5-110">[out] Recibe el nombre de la clase a la que pertenece el método.</span><span class="sxs-lookup"><span data-stu-id="93aa5-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="93aa5-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="93aa5-111">Return value</span></span>

<span data-ttu-id="93aa5-112">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="93aa5-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="93aa5-113">Constante</span><span class="sxs-lookup"><span data-stu-id="93aa5-113">Constant</span></span>  |<span data-ttu-id="93aa5-114">Valor</span><span class="sxs-lookup"><span data-stu-id="93aa5-114">Value</span></span>  |<span data-ttu-id="93aa5-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="93aa5-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="93aa5-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="93aa5-116">0x80041002</span></span> | <span data-ttu-id="93aa5-117">No se encontró el método especificado.</span><span class="sxs-lookup"><span data-stu-id="93aa5-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="93aa5-118">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="93aa5-118">0x80041008</span></span> | <span data-ttu-id="93aa5-119">Uno o más parámetros no son válidos.</span><span class="sxs-lookup"><span data-stu-id="93aa5-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="93aa5-120">0</span><span class="sxs-lookup"><span data-stu-id="93aa5-120">0</span></span> | <span data-ttu-id="93aa5-121">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="93aa5-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="93aa5-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="93aa5-122">Remarks</span></span>

<span data-ttu-id="93aa5-123">Esta función contiene una llamada a la [IWbemClassObject::GetMethodOrigin](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="93aa5-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](https://msdn.microsoft.com/library/aa391443(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="93aa5-124">Dado que una clase puede heredar métodos de una o más clases base, los programadores a menudo desean determinar la clase en la que se define un método determinado.</span><span class="sxs-lookup"><span data-stu-id="93aa5-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="93aa5-125">El `pstrClassName` parámetro no debe apuntar a válido `BSTR` antes de llama a la función porque se trata de un `out` parámetro; en este puntero no se cancela la asignación después de la función devuelve.</span><span class="sxs-lookup"><span data-stu-id="93aa5-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="93aa5-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="93aa5-126">Requirements</span></span>  
<span data-ttu-id="93aa5-127">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="93aa5-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="93aa5-128">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="93aa5-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="93aa5-129">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="93aa5-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="93aa5-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="93aa5-130">See also</span></span>  
[<span data-ttu-id="93aa5-131">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="93aa5-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
