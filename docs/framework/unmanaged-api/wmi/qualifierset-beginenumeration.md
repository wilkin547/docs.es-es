---
title: "Función QualifierSet_BeginEnumeration (referencia de API no administrada)"
description: "La función QualifierSet_BeginEnumeration restablece el enumerador de los calificadores de un objeto."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_BeginEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_BeginEnumeration
helpviewer_keywords: QualifierSet_BeginEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 440dde03f4ed138a33eb6f817723d7c5c74f6d46
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="qualifiersetbeginenumeration-function"></a><span data-ttu-id="51329-103">QualifierSet_BeginEnumeration (función)</span><span class="sxs-lookup"><span data-stu-id="51329-103">QualifierSet_BeginEnumeration function</span></span>
<span data-ttu-id="51329-104">Restablece el enumerador de los calificadores de un objeto al principio de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="51329-104">Resets an enumerator of the qualifiers of an object to the beginning of the enumeration.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="51329-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="51329-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_BeginEnumeration (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="51329-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="51329-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="51329-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="51329-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="51329-108">[in] Un puntero a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="51329-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`lFlags`   
<span data-ttu-id="51329-109">[in] Una combinación bit a bit de los indicadores o valores que se describen en la [comentarios](#remarks) sección que especifica los calificadores que se incluirán en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="51329-109">[in] A bitwise combination of the flags or values described in the [Remarks](#remarks) section that specifies the qualifiers to include in the enumeration.</span></span>

## <a name="return-value"></a><span data-ttu-id="51329-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="51329-110">Return value</span></span>

<span data-ttu-id="51329-111">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="51329-111">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="51329-112">Constante</span><span class="sxs-lookup"><span data-stu-id="51329-112">Constant</span></span>  |<span data-ttu-id="51329-113">Valor</span><span class="sxs-lookup"><span data-stu-id="51329-113">Value</span></span>  |<span data-ttu-id="51329-114">Descripción</span><span class="sxs-lookup"><span data-stu-id="51329-114">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="51329-115">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="51329-115">0x80041008</span></span> | <span data-ttu-id="51329-116">El `lFlags` parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="51329-116">The `lFlags` parameter is not valid.</span></span> |
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="51329-117">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="51329-117">0x8004101d</span></span> | <span data-ttu-id="51329-118">Una segunda llamada a `QualifierSet_BeginEnumeration` se realizó sin una llamada intermedia a [ `QualifierSet_EndEnumeration` ](qualifierset-endenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="51329-118">A second call to `QualifierSet_BeginEnumeration` was made without an intervening call to [`QualifierSet_EndEnumeration`](qualifierset-endenumeration.md).</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="51329-119">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="51329-119">0x80041006</span></span> | <span data-ttu-id="51329-120">No hay suficiente memoria disponible para iniciar una nueva enumeración.</span><span class="sxs-lookup"><span data-stu-id="51329-120">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="51329-121">0</span><span class="sxs-lookup"><span data-stu-id="51329-121">0</span></span> | <span data-ttu-id="51329-122">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="51329-122">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="51329-123">Comentarios</span><span class="sxs-lookup"><span data-stu-id="51329-123">Remarks</span></span>

<span data-ttu-id="51329-124">Esta función contiene una llamada a la [IWbemQualifierSet::BeginEnumeration](https://msdn.microsoft.com/library/aa391861(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="51329-124">This function wraps a call to the [IWbemQualifierSet::BeginEnumeration](https://msdn.microsoft.com/library/aa391861(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="51329-125">Para enumerar todos los calificadores en un objeto, debe llamar a este método antes de la primera llamada a [QualifierSet_Next](qualifierset-next.md).</span><span class="sxs-lookup"><span data-stu-id="51329-125">To enumerate all of the qualifiers on an object, this method must be called before the first call to [QualifierSet_Next](qualifierset-next.md).</span></span> <span data-ttu-id="51329-126">Se garantiza el orden en el que se enumeran los calificadores que puede variar con respecto de una enumeración especificada.</span><span class="sxs-lookup"><span data-stu-id="51329-126">The order in which qualifiers are enumerated is guaranteed to be invariant for a given enumeration.</span></span>

<span data-ttu-id="51329-127">Las marcas que se pueden pasar como el `lEnumFlags` argumento se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código.</span><span class="sxs-lookup"><span data-stu-id="51329-127">The flags that can be passed as the `lEnumFlags` argument are defined in the *WbemCli.h* header file, or you can define them as constants in your code.</span></span>   

|<span data-ttu-id="51329-128">Constante</span><span class="sxs-lookup"><span data-stu-id="51329-128">Constant</span></span>  |<span data-ttu-id="51329-129">Valor</span><span class="sxs-lookup"><span data-stu-id="51329-129">Value</span></span>  |<span data-ttu-id="51329-130">Descripción</span><span class="sxs-lookup"><span data-stu-id="51329-130">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="51329-131">0</span><span class="sxs-lookup"><span data-stu-id="51329-131">0</span></span> | <span data-ttu-id="51329-132">Devolver los nombres de todos los calificadores.</span><span class="sxs-lookup"><span data-stu-id="51329-132">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="51329-133">0 x 10</span><span class="sxs-lookup"><span data-stu-id="51329-133">0x10</span></span> | <span data-ttu-id="51329-134">Devolver solo los nombres de calificadores específicos que el objeto o la propiedad actual.</span><span class="sxs-lookup"><span data-stu-id="51329-134">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="51329-135">Para una propiedad: devolver solo los calificadores específicos a la propiedad (incluidas las invalidaciones) y no los calificadores se propagan desde la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="51329-135">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="51329-136">Para una instancia: devolver solo los nombres de calificador de específicos de la instancia.</span><span class="sxs-lookup"><span data-stu-id="51329-136">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="51329-137">Para una clase: devolver solo calificadores específicos a la beiong de la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="51329-137">For a class: Return only qualifiers specific to the class beiong derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="51329-138">0 x 20</span><span class="sxs-lookup"><span data-stu-id="51329-138">0x20</span></span> | <span data-ttu-id="51329-139">Devuelve solo los nombres de calificadores propagan de otro objeto.</span><span class="sxs-lookup"><span data-stu-id="51329-139">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="51329-140">Para una propiedad: devuelven solo los calificadores se propagan a esta propiedad en la definición de clase y no los de la propiedad en Sí.</span><span class="sxs-lookup"><span data-stu-id="51329-140">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="51329-141">Para una instancia: devolución propagan sólo los calificadores de la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="51329-141">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="51329-142">Para una clase: devolver sólo los nombres de calificador que se heredaron de las clases principales.</span><span class="sxs-lookup"><span data-stu-id="51329-142">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

## <a name="requirements"></a><span data-ttu-id="51329-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="51329-143">Requirements</span></span>  
 <span data-ttu-id="51329-144">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="51329-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="51329-145">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="51329-145">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="51329-146">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="51329-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51329-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="51329-147">See also</span></span>  
[<span data-ttu-id="51329-148">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="51329-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
