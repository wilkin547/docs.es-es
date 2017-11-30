---
title: "Función QualifierSet_Put (referencia de API no administrada)"
description: "La función QualifierSet_Put escribe el calificador con nombre y su valor."
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: QualifierSet_Put
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: QualifierSet_Put
helpviewer_keywords: QualifierSet_Put function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 7fdb6759d4e39ad9ab6bd6da2c2a0e2abfbe5d56
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="qualifiersetput-function"></a><span data-ttu-id="16b77-103">QualifierSet_Put (función)</span><span class="sxs-lookup"><span data-stu-id="16b77-103">QualifierSet_Put function</span></span>
<span data-ttu-id="16b77-104">Escribe el valor y calificador con nombre.</span><span class="sxs-lookup"><span data-stu-id="16b77-104">Writes the named qualifier and value.</span></span> <span data-ttu-id="16b77-105">El nuevo calificador sobrescribe el valor anterior del mismo nombre.</span><span class="sxs-lookup"><span data-stu-id="16b77-105">The new qualifier overwrites the previous value of the same name.</span></span> <span data-ttu-id="16b77-106">Si el calificador no existe, se crea.</span><span class="sxs-lookup"><span data-stu-id="16b77-106">If the qualifier does not exist, it is created.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="16b77-107">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="16b77-107">Syntax</span></span>  
  
```  
HRESULT QualifierSet_Put (
   [in] int                  vFunc, 
   [in] IWbemQualifierSet*   ptr, 
   [in] LPCWSTR              wszName,
   [in] VARIANT*             pVal,
   [in] LONG                 lFlavor
); 
```  

## <a name="parameters"></a><span data-ttu-id="16b77-108">Parámetros</span><span class="sxs-lookup"><span data-stu-id="16b77-108">Parameters</span></span>

`vFunc`   
<span data-ttu-id="16b77-109">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="16b77-109">[in] This parameter is unused.</span></span>

`ptr`   
<span data-ttu-id="16b77-110">[in] Un puntero a un [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="16b77-110">[in] A pointer to an [IWbemQualifierSet](https://msdn.microsoft.com/library/aa391860(v=vs.85).aspx) instance.</span></span>

`wszName`   
<span data-ttu-id="16b77-111">[in] El nombre del calificador que se va a escribir.</span><span class="sxs-lookup"><span data-stu-id="16b77-111">[in] The name of the qualifier to write.</span></span>

<span data-ttu-id="16b77-112">`pVal`[in] Un puntero a un válido `VARIANT` que contiene el calificador que desea escribir.</span><span class="sxs-lookup"><span data-stu-id="16b77-112">`pVal` [in] A pointer to a valid `VARIANT` that contains the qualifier to write.</span></span> <span data-ttu-id="16b77-113">Este parámetro no puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="16b77-113">This parameter cannot be `null`.</span></span>

<span data-ttu-id="16b77-114">`lFlavor`[in] Una de las constantes siguientes que define los tipos de calificador deseada para este calificador.</span><span class="sxs-lookup"><span data-stu-id="16b77-114">`lFlavor` [in] One of the following constants that defines the desired qualifier flavors for this qualifier.</span></span> <span data-ttu-id="16b77-115">El valor predeterminado es `WBEM_FLAVOR_OVERRIDABLE` (0).</span><span class="sxs-lookup"><span data-stu-id="16b77-115">The default value is `WBEM_FLAVOR_OVERRIDABLE` (0).</span></span>

|<span data-ttu-id="16b77-116">Constante</span><span class="sxs-lookup"><span data-stu-id="16b77-116">Constant</span></span>  |<span data-ttu-id="16b77-117">Valor</span><span class="sxs-lookup"><span data-stu-id="16b77-117">Value</span></span>  |<span data-ttu-id="16b77-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="16b77-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_OVERRIDABLE` | <span data-ttu-id="16b77-119">0</span><span class="sxs-lookup"><span data-stu-id="16b77-119">0</span></span> | <span data-ttu-id="16b77-120">El calificador puede invalidarse en una clase derivada o una instancia.</span><span class="sxs-lookup"><span data-stu-id="16b77-120">The qualifier can be overridden in a derived class or instance.</span></span> <span data-ttu-id="16b77-121">**Este es el valor predeterminado.**</span><span class="sxs-lookup"><span data-stu-id="16b77-121">**This is the default value.**</span></span> |
| `WBEM_FLAVOR_FLAG_PROPAGATE_TO_INSTANCE` | <span data-ttu-id="16b77-122">1</span><span class="sxs-lookup"><span data-stu-id="16b77-122">1</span></span> | <span data-ttu-id="16b77-123">El calificador se propaga a las instancias.</span><span class="sxs-lookup"><span data-stu-id="16b77-123">The qualifier is propagated to instances.</span></span> |
| `WBEM_FLAVOR_GLAG_PROPAGATE_TO_DERIVED_CLASS` | <span data-ttu-id="16b77-124">2</span><span class="sxs-lookup"><span data-stu-id="16b77-124">2</span></span> | <span data-ttu-id="16b77-125">El calificador se propaga a las clases derivadas.</span><span class="sxs-lookup"><span data-stu-id="16b77-125">The qualifier is propagated to derived classes.</span></span> |
| <span data-ttu-id="16b77-126">' WBEM_FLAVOR_NOT_OVERRIDABLE</span><span class="sxs-lookup"><span data-stu-id="16b77-126">\`WBEM_FLAVOR_NOT_OVERRIDABLE</span></span> | <span data-ttu-id="16b77-127">0 x 10</span><span class="sxs-lookup"><span data-stu-id="16b77-127">0x10</span></span> | <span data-ttu-id="16b77-128">El calificador no puede invalidarse en una clase o instancia derivada.</span><span class="sxs-lookup"><span data-stu-id="16b77-128">The qualifier cannot be overridden in a derived class or instance.</span></span> |
| <span data-ttu-id="16b77-129">' WBEM_FLAVOR_AMENDED</span><span class="sxs-lookup"><span data-stu-id="16b77-129">\`WBEM_FLAVOR_AMENDED</span></span> | <span data-ttu-id="16b77-130">0 x 80</span><span class="sxs-lookup"><span data-stu-id="16b77-130">0x80</span></span> | <span data-ttu-id="16b77-131">El calificador se localiza.</span><span class="sxs-lookup"><span data-stu-id="16b77-131">The qualifier is localized.</span></span> |

## <a name="return-value"></a><span data-ttu-id="16b77-132">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="16b77-132">Return value</span></span>

<span data-ttu-id="16b77-133">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="16b77-133">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="16b77-134">Constante</span><span class="sxs-lookup"><span data-stu-id="16b77-134">Constant</span></span>  |<span data-ttu-id="16b77-135">Valor</span><span class="sxs-lookup"><span data-stu-id="16b77-135">Value</span></span>  |<span data-ttu-id="16b77-136">Descripción</span><span class="sxs-lookup"><span data-stu-id="16b77-136">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_CANNOT_BE_KEY` | <span data-ttu-id="16b77-137">0x8004101f</span><span class="sxs-lookup"><span data-stu-id="16b77-137">0x8004101f</span></span> | <span data-ttu-id="16b77-138">Se produjo un intento no válido para especificar el **clave** calificador en una propiedad que no puede ser una clave.</span><span class="sxs-lookup"><span data-stu-id="16b77-138">There was an illegal attempt to specify the **Key** qualifier on a property that cannot be a key.</span></span> <span data-ttu-id="16b77-139">Las claves se especifican om c; definición ase para un objeto y no se pueden alterar en por instancia.</span><span class="sxs-lookup"><span data-stu-id="16b77-139">The keys are specified om tje c;ass definition for an object and cannot be altered on a per-instance basis.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="16b77-140">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="16b77-140">0x80041008</span></span> | <span data-ttu-id="16b77-141">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="16b77-141">A parameter is not valid.</span></span> |
| `WBEM_E_INVALID_QUALIFIER_TYPE` | <span data-ttu-id="16b77-142">0x80041029</span><span class="sxs-lookup"><span data-stu-id="16b77-142">0x80041029</span></span> | <span data-ttu-id="16b77-143">El `pVal` parámetro no es de un tipo de certificador válido.</span><span class="sxs-lookup"><span data-stu-id="16b77-143">The `pVal` parameter is not of a legal qualifier type.</span></span> |
| `WBEM_E_OVERRIDE_NOT_ALLOWED` | <span data-ttu-id="16b77-144">0x8004101a</span><span class="sxs-lookup"><span data-stu-id="16b77-144">0x8004101a</span></span> | <span data-ttu-id="16b77-145">No es posible llamar a la `QualifierSet_Put` método en el calificador porque el objeto propietario no permite invalida.</span><span class="sxs-lookup"><span data-stu-id="16b77-145">It is not possible to call the `QualifierSet_Put` method on the qualifier because the owning object does not permit overrides.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="16b77-146">0</span><span class="sxs-lookup"><span data-stu-id="16b77-146">0</span></span> | <span data-ttu-id="16b77-147">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="16b77-147">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="16b77-148">Comentarios</span><span class="sxs-lookup"><span data-stu-id="16b77-148">Remarks</span></span>

<span data-ttu-id="16b77-149">Esta función contiene una llamada a la [IWbemQualifierSet::Put](https://msdn.microsoft.com/library/aa391871(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="16b77-149">This function wraps a call to the [IWbemQualifierSet::Put](https://msdn.microsoft.com/library/aa391871(v=vs.85).aspx) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="16b77-150">Requisitos</span><span class="sxs-lookup"><span data-stu-id="16b77-150">Requirements</span></span>  
 <span data-ttu-id="16b77-151">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="16b77-151">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="16b77-152">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="16b77-152">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="16b77-153">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="16b77-153">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="16b77-154">Vea también</span><span class="sxs-lookup"><span data-stu-id="16b77-154">See also</span></span>  
[<span data-ttu-id="16b77-155">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="16b77-155">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
