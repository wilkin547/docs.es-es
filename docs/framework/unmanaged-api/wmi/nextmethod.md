---
title: "Función NextMethod (referencia de API no administrada)"
description: "La función NextMethod recupera el método siguiente en una enumeración."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: NextMethod
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: NextMethod
helpviewer_keywords: NextMethod function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 6b886b3ecbd1d5b5b8d212846b2bd8291fa43909
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="nextmethod-function"></a><span data-ttu-id="98908-103">NextMethod (función)</span><span class="sxs-lookup"><span data-stu-id="98908-103">NextMethod function</span></span>
<span data-ttu-id="98908-104">Recupera el siguiente método de enumeración que comienza con una llamada a [BeginMethodEnumeration](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="98908-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="98908-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="98908-105">Syntax</span></span>  
  
```  
HRESULT NextMethod (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature   
); 
```  

## <a name="parameters"></a><span data-ttu-id="98908-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="98908-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="98908-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="98908-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="98908-108">[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="98908-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="98908-109">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="98908-109">[in] Reserved.</span></span> <span data-ttu-id="98908-110">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="98908-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="98908-111">[out] Un puntero que señala a `null` antes de la llamada.</span><span class="sxs-lookup"><span data-stu-id="98908-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="98908-112">Cuando se devuelve la función, la dirección de un nuevo `BSTR` que contiene el nombre del método.</span><span class="sxs-lookup"><span data-stu-id="98908-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span> 

`ppSignatureIn`  
<span data-ttu-id="98908-113">[out] Un puntero que recibe un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) que contiene el `in` parámetros para el método.</span><span class="sxs-lookup"><span data-stu-id="98908-113">[out] A pointer that receives a pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) that contains the `in` parameters for the method.</span></span> 

`ppSignatureOut`  
<span data-ttu-id="98908-114">[out] Un puntero que recibe un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) que contiene el `out` parámetros para el método.</span><span class="sxs-lookup"><span data-stu-id="98908-114">[out] A pointer that receives a pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) that contains the `out` parameters for the method.</span></span> 

## <a name="return-value"></a><span data-ttu-id="98908-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="98908-115">Return value</span></span>

<span data-ttu-id="98908-116">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="98908-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="98908-117">Constante</span><span class="sxs-lookup"><span data-stu-id="98908-117">Constant</span></span>  |<span data-ttu-id="98908-118">Valor</span><span class="sxs-lookup"><span data-stu-id="98908-118">Value</span></span>  |<span data-ttu-id="98908-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="98908-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="98908-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="98908-120">0x8004101d</span></span> | <span data-ttu-id="98908-121">Se ha producido ninguna llamada a la [ `BeginEnumeration` ](beginenumeration.md) (función).</span><span class="sxs-lookup"><span data-stu-id="98908-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="98908-122">0</span><span class="sxs-lookup"><span data-stu-id="98908-122">0</span></span> | <span data-ttu-id="98908-123">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="98908-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="98908-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="98908-124">0x40005</span></span> | <span data-ttu-id="98908-125">No hay ninguna propiedad más en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="98908-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="98908-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="98908-126">Remarks</span></span>

<span data-ttu-id="98908-127">Esta función contiene una llamada a la [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="98908-127">This function wraps a call to the [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="98908-128">El llamador inicia la secuencia de enumeración mediante una llamada a la [BeginMethodEnumeration](beginmethodenumeration.md) función y, a continuación, llama a la función [NextMethod] hasta que regresa la función `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="98908-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="98908-129">Si lo desea, el llamador finaliza la secuencia mediante una llamada a [EndMethodEnumeration](endmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="98908-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="98908-130">El llamador puede finalizar la enumeración al principio mediante una llamada a [EndMethodEnumeration](endmethodenumeration.md) en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="98908-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="98908-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="98908-131">Example</span></span>

<span data-ttu-id="98908-132">Para obtener un ejemplo de C++, vea la [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="98908-132">For a C++ example, see the [IWbemClassObject::NextMethod](https://msdn.microsoft.com/library/aa391454(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="98908-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="98908-133">Requirements</span></span>  
 <span data-ttu-id="98908-134">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="98908-134">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="98908-135">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="98908-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="98908-136">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="98908-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="98908-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="98908-137">See also</span></span>  
[<span data-ttu-id="98908-138">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="98908-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
