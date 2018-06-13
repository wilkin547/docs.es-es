---
title: Get (función) (referencia de API no administrada)
description: La función Get recupera el valor de propiedad especificado.
ms.date: 11/06/2017
api_name:
- Get
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Get
helpviewer_keywords:
- Get function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 2f837a526879f80177bc9979e1d7671edfcd8d4f
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460153"
---
# <a name="get-function"></a><span data-ttu-id="221eb-103">Get (función)</span><span class="sxs-lookup"><span data-stu-id="221eb-103">Get function</span></span>
<span data-ttu-id="221eb-104">Recupera el valor de la propiedad especificada, si existe.</span><span class="sxs-lookup"><span data-stu-id="221eb-104">Retrieves the specified property value if it exists.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="221eb-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="221eb-105">Syntax</span></span>  
  
```  
HRESULT Get (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName,
   [in] LONG              lFlags,
   [out] VARIANT*         pVal,
   [out] CIMTYPE*         pvtType,
   [out] LONG*            plFlavor
); 
```  

## <a name="parameters"></a><span data-ttu-id="221eb-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="221eb-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="221eb-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="221eb-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="221eb-108">[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="221eb-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`wszName`  
<span data-ttu-id="221eb-109">[in] El nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="221eb-109">[in] The name of the property.</span></span>

<span data-ttu-id="221eb-110">`lFlags` [in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="221eb-110">`lFlags` [in] Reserved.</span></span> <span data-ttu-id="221eb-111">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="221eb-111">This parameter must be 0.</span></span>

<span data-ttu-id="221eb-112">`pVal` [out] Si la función devuelve correctamente, contiene el valor de la `wszName` propiedad.</span><span class="sxs-lookup"><span data-stu-id="221eb-112">`pVal` [out] If the function returns successfully, contains the value of the `wszName` property.</span></span> <span data-ttu-id="221eb-113">El `pval` argumento se asigna el tipo correcto y el valor del calificador.</span><span class="sxs-lookup"><span data-stu-id="221eb-113">The `pval` argument is assigned the correct type and value for the qualifier.</span></span>

<span data-ttu-id="221eb-114">`pvtType` [out] Si la función devuelve correctamente, contiene un [constante de tipo de CIM](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) que indica el tipo de propiedad.</span><span class="sxs-lookup"><span data-stu-id="221eb-114">`pvtType` [out] If the function returns successfully, contains a [CIM-type constant](https://msdn.microsoft.com/library/aa386309(v=vs.85).aspx) that indicates the property type.</span></span> <span data-ttu-id="221eb-115">Su valor puede ser también `null`.</span><span class="sxs-lookup"><span data-stu-id="221eb-115">Its value can also be `null`.</span></span> 

<span data-ttu-id="221eb-116">`plFlavor` [out] Si la función devuelve correctamente, recibe información sobre el origen de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="221eb-116">`plFlavor` [out] If the function returns successfully, receives information about the origin of the property.</span></span> <span data-ttu-id="221eb-117">Su valor puede ser `null`, o una de las siguientes constantes WBEM_FLAVOR_TYPE definidas en el *WbemCli.h* archivo de encabezado:</span><span class="sxs-lookup"><span data-stu-id="221eb-117">Its value can be `null`, or one of the following WBEM_FLAVOR_TYPE constants defined in the *WbemCli.h* header file:</span></span> 

|<span data-ttu-id="221eb-118">Constante</span><span class="sxs-lookup"><span data-stu-id="221eb-118">Constant</span></span>  |<span data-ttu-id="221eb-119">Valor</span><span class="sxs-lookup"><span data-stu-id="221eb-119">Value</span></span>  |<span data-ttu-id="221eb-120">Descripción</span><span class="sxs-lookup"><span data-stu-id="221eb-120">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAVOR_ORIGIN_SYSTEM` | <span data-ttu-id="221eb-121">0x40</span><span class="sxs-lookup"><span data-stu-id="221eb-121">0x40</span></span> | <span data-ttu-id="221eb-122">La propiedad es una propiedad estándar del sistema.</span><span class="sxs-lookup"><span data-stu-id="221eb-122">The property is a standard system property.</span></span> |
| `WBEM_FLAVOR_ORIGIN_PROPAGATED` | <span data-ttu-id="221eb-123">0 x 20</span><span class="sxs-lookup"><span data-stu-id="221eb-123">0x20</span></span> | <span data-ttu-id="221eb-124">Para una clase: la propiedad se hereda de la clase primaria.</span><span class="sxs-lookup"><span data-stu-id="221eb-124">For a class: The property is inherited from the parent class.</span></span> </br> <span data-ttu-id="221eb-125">Para una instancia: la propiedad, mientras que se hereda de la clase primaria, no ha sido modificada por la instancia.</span><span class="sxs-lookup"><span data-stu-id="221eb-125">For an instance: The property, while inherited from the parent class, has not been modified by the instance.</span></span>  |
| `WBEM_FLAVOR_ORIGIN_LOCAL` | <span data-ttu-id="221eb-126">0</span><span class="sxs-lookup"><span data-stu-id="221eb-126">0</span></span> | <span data-ttu-id="221eb-127">Para una clase: la propiedad pertenece a la clase derivada.</span><span class="sxs-lookup"><span data-stu-id="221eb-127">For a class: The property belongs to the derived class.</span></span> </br> <span data-ttu-id="221eb-128">Para una instancia: la propiedad se modifica la instancia; es decir, se proporcionó un valor o un calificador se ha agregado o modificado.</span><span class="sxs-lookup"><span data-stu-id="221eb-128">For an instance: The property is modified by the instance; that is, a value was supplied, or a qualifier was added or modified.</span></span> |

## <a name="return-value"></a><span data-ttu-id="221eb-129">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="221eb-129">Return value</span></span>

<span data-ttu-id="221eb-130">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="221eb-130">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="221eb-131">Constante</span><span class="sxs-lookup"><span data-stu-id="221eb-131">Constant</span></span>  |<span data-ttu-id="221eb-132">Valor</span><span class="sxs-lookup"><span data-stu-id="221eb-132">Value</span></span>  |<span data-ttu-id="221eb-133">Descripción</span><span class="sxs-lookup"><span data-stu-id="221eb-133">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="221eb-134">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="221eb-134">0x80041001</span></span> | <span data-ttu-id="221eb-135">Ha habido un error general.</span><span class="sxs-lookup"><span data-stu-id="221eb-135">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="221eb-136">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="221eb-136">0x80041008</span></span> | <span data-ttu-id="221eb-137">Uno o más parámetros no son válidos.</span><span class="sxs-lookup"><span data-stu-id="221eb-137">One or more parameters are not valid.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="221eb-138">0x80041002</span><span class="sxs-lookup"><span data-stu-id="221eb-138">0x80041002</span></span> | <span data-ttu-id="221eb-139">No se encontró la propiedad especificada.</span><span class="sxs-lookup"><span data-stu-id="221eb-139">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="221eb-140">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="221eb-140">0x80041006</span></span> | <span data-ttu-id="221eb-141">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="221eb-141">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="221eb-142">0</span><span class="sxs-lookup"><span data-stu-id="221eb-142">0</span></span> | <span data-ttu-id="221eb-143">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="221eb-143">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="221eb-144">Comentarios</span><span class="sxs-lookup"><span data-stu-id="221eb-144">Remarks</span></span>

<span data-ttu-id="221eb-145">Esta función contiene una llamada a la [IWbemClassObject::Get](https://msdn.microsoft.com/library/aa391442(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="221eb-145">This function wraps a call to the [IWbemClassObject::Get](https://msdn.microsoft.com/library/aa391442(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="221eb-146">El `Get` función también puede devolver propiedades del sistema.</span><span class="sxs-lookup"><span data-stu-id="221eb-146">The `Get` function can also return system properties.</span></span>

<span data-ttu-id="221eb-147">El `pVal` argumento se asigna al tipo correcto y valor para el calificador y el COM [VariantInit](https://msdn.microsoft.com/library/ms221402(v=vs.85).aspx) (función)</span><span class="sxs-lookup"><span data-stu-id="221eb-147">The `pVal` argument is assigned the correct type and value for the qualifier and the COM [VariantInit](https://msdn.microsoft.com/library/ms221402(v=vs.85).aspx) function</span></span>

## <a name="requirements"></a><span data-ttu-id="221eb-148">Requisitos</span><span class="sxs-lookup"><span data-stu-id="221eb-148">Requirements</span></span>  
 <span data-ttu-id="221eb-149">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="221eb-149">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="221eb-150">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="221eb-150">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="221eb-151">**Versiones de .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="221eb-151">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="221eb-152">Vea también</span><span class="sxs-lookup"><span data-stu-id="221eb-152">See also</span></span>  
[<span data-ttu-id="221eb-153">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="221eb-153">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
