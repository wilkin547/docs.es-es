---
title: "Función QualifierSet_GetNames (referencia de API no administrada)"
description: "La función QualifierSet_GetNames recupera los nombres de calificadores de un objeto o una propiedad."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_GetNames
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_GetNames
helpviewer_keywords: QualifierSet_GetNames function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: b87518bdc1f6ac19eb48991538be5904fdb63f1f
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetgetnames-function"></a><span data-ttu-id="fb91d-103">QualifierSet_GetNames (función)</span><span class="sxs-lookup"><span data-stu-id="fb91d-103">QualifierSet_GetNames function</span></span>
<span data-ttu-id="fb91d-104">Recupera los nombres de todos los calificadores o de ciertos calificadores que están disponibles en el objeto actual o la propiedad.</span><span class="sxs-lookup"><span data-stu-id="fb91d-104">Retrieves the names of all the qualifiers or of certain qualifiers that are available from the current object or property.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="fb91d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="fb91d-105">Syntax</span></span>  
  
```  
HRESULT QualifierSet_GetNames (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LONG                 lFlags,
   [out] SAFEARRAY (BSTR)**  pstrNames
); 
```  

## <a name="parameters"></a><span data-ttu-id="fb91d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="fb91d-106">Parameters</span></span>

`vFunc`   
<span data-ttu-id="fb91d-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="fb91d-107">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="fb91d-108">[in] Un puntero a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="fb91d-108">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`lFlags`   
<span data-ttu-id="fb91d-109">[in] Uno de los siguientes indicadores o valores que especifica los nombres que desee incluir en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="fb91d-109">[in] One of the following flags or values that specifies which names to include in the enumeration.</span></span>

|<span data-ttu-id="fb91d-110">Constante</span><span class="sxs-lookup"><span data-stu-id="fb91d-110">Constant</span></span>  |<span data-ttu-id="fb91d-111">Valor</span><span class="sxs-lookup"><span data-stu-id="fb91d-111">Value</span></span>  |<span data-ttu-id="fb91d-112">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb91d-112">Description</span></span>  |
|---------|---------|---------|
|  | <span data-ttu-id="fb91d-113">0</span><span class="sxs-lookup"><span data-stu-id="fb91d-113">0</span></span> | <span data-ttu-id="fb91d-114">Devolver los nombres de todos los calificadores.</span><span class="sxs-lookup"><span data-stu-id="fb91d-114">Return the names of all qualifiers.</span></span> |
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="fb91d-115">0 x 10</span><span class="sxs-lookup"><span data-stu-id="fb91d-115">0x10</span></span> | <span data-ttu-id="fb91d-116">Devolver solo los nombres de calificadores específicos que el objeto o la propiedad actual.</span><span class="sxs-lookup"><span data-stu-id="fb91d-116">Return only the names of qualifiers specific to the current property or object.</span></span> <br/> <span data-ttu-id="fb91d-117">Para una propiedad: devolver solo los calificadores específicos a la propiedad (incluidas las invalidaciones) y no los calificadores se propagan desde la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="fb91d-117">For a property: Return only the qualifiers specific to the property (including overrides), and not those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="fb91d-118">Para una instancia: devolver solo los nombres de calificador de específicos de la instancia.</span><span class="sxs-lookup"><span data-stu-id="fb91d-118">For an instance: Return only instance-specific qualifier names.</span></span> <br/> <span data-ttu-id="fb91d-119">Para una clase: devolver solo calificadores específicos a la beiong de la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="fb91d-119">For a class: Return only qualifiers specific to the class beiong derived.</span></span>
|`WBEM_FLAG_PROPAGATED_ONLY` | <span data-ttu-id="fb91d-120">0 x 20</span><span class="sxs-lookup"><span data-stu-id="fb91d-120">0x20</span></span> | <span data-ttu-id="fb91d-121">Devuelve solo los nombres de calificadores propagan de otro objeto.</span><span class="sxs-lookup"><span data-stu-id="fb91d-121">Return only the names of qualifiers propagated from another object.</span></span> <br/> <span data-ttu-id="fb91d-122">Para una propiedad: devuelven solo los calificadores se propagan a esta propiedad en la definición de clase y no los de la propiedad en Sí.</span><span class="sxs-lookup"><span data-stu-id="fb91d-122">For a property: Return only the qualifiers propagated to this property from the class definition, and not those from the property itself.</span></span> <br/> <span data-ttu-id="fb91d-123">Para una instancia: devolución propagan sólo los calificadores de la definición de clase.</span><span class="sxs-lookup"><span data-stu-id="fb91d-123">For an instance: Return only those qualifiers propagated from the class definition.</span></span> <br/> <span data-ttu-id="fb91d-124">Para una clase: devolver sólo los nombres de calificador que se heredaron de las clases principales.</span><span class="sxs-lookup"><span data-stu-id="fb91d-124">For a class: Return only those qualifier names inherited from the parent classes.</span></span> |

<span data-ttu-id="fb91d-125">`pstrNames`[out] Un nuevo `SAFEARRAY` que contiene los nombres solicitados.</span><span class="sxs-lookup"><span data-stu-id="fb91d-125">`pstrNames` [out] A new `SAFEARRAY` that contains the requested names.</span></span> <span data-ttu-id="fb91d-126">La matriz puede tener 0 elementos.</span><span class="sxs-lookup"><span data-stu-id="fb91d-126">The array can have 0 elements.</span></span> <span data-ttu-id="fb91d-127">Si se produce un error, un nuevo `SAFEARRAY` no se devuelve.</span><span class="sxs-lookup"><span data-stu-id="fb91d-127">If an error occurs, a new `SAFEARRAY` is not returned.</span></span>

## <a name="return-value"></a><span data-ttu-id="fb91d-128">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="fb91d-128">Return value</span></span>

<span data-ttu-id="fb91d-129">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="fb91d-129">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="fb91d-130">Constante</span><span class="sxs-lookup"><span data-stu-id="fb91d-130">Constant</span></span>  |<span data-ttu-id="fb91d-131">Valor</span><span class="sxs-lookup"><span data-stu-id="fb91d-131">Value</span></span>  |<span data-ttu-id="fb91d-132">Descripción</span><span class="sxs-lookup"><span data-stu-id="fb91d-132">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="fb91d-133">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="fb91d-133">0x80041008</span></span> | <span data-ttu-id="fb91d-134">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="fb91d-134">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="fb91d-135">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="fb91d-135">0x80041006</span></span> | <span data-ttu-id="fb91d-136">No hay suficiente memoria disponible para iniciar una nueva enumeración.</span><span class="sxs-lookup"><span data-stu-id="fb91d-136">Not enough memory is available to begin a new enumeration.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="fb91d-137">0</span><span class="sxs-lookup"><span data-stu-id="fb91d-137">0</span></span> | <span data-ttu-id="fb91d-138">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="fb91d-138">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="fb91d-139">Comentarios</span><span class="sxs-lookup"><span data-stu-id="fb91d-139">Remarks</span></span>

<span data-ttu-id="fb91d-140">Esta función contiene una llamada a la [IWbemQualifierSet::GetNames](https://msdn.microsoft.com/library/aa391868(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="fb91d-140">This function wraps a call to the [IWbemQualifierSet::GetNames](https://msdn.microsoft.com/library/aa391868(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="fb91d-141">Una vez que haya recuperado los nombres de calificador, se puede tener acceso a cada calificador por su nombre mediante una llamada a la [QualifierSet_Get](qualifierset-get.md) (función).</span><span class="sxs-lookup"><span data-stu-id="fb91d-141">Once you've retrieved the qualifier names, you can access each qualifier by name by calling the [QualifierSet_Get](qualifierset-get.md) function.</span></span> 

<span data-ttu-id="fb91d-142">No es un error de un determinado objeto de tener cero calificadores, por lo que el número de cadenas en `pstrNames` en el valor devuelto puede ser 0, incluso si la función devuelve `WBEM_S_NO_ERROR`.</span><span class="sxs-lookup"><span data-stu-id="fb91d-142">It is not an error for a given object to have zero qualifiers, so the number of strings in `pstrNames` on return can be 0, even though the function returns `WBEM_S_NO_ERROR`.</span></span>

## <a name="requirements"></a><span data-ttu-id="fb91d-143">Requisitos</span><span class="sxs-lookup"><span data-stu-id="fb91d-143">Requirements</span></span>  
 <span data-ttu-id="fb91d-144">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="fb91d-144">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fb91d-145">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="fb91d-145">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="fb91d-146">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="fb91d-146">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fb91d-147">Vea también</span><span class="sxs-lookup"><span data-stu-id="fb91d-147">See also</span></span>  
[<span data-ttu-id="fb91d-148">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="fb91d-148">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
