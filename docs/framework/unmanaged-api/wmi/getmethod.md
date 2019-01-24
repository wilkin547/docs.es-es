---
title: GetMethod (función) (referencia de API no administrada)
description: La función GetMethod recupera información sobre un método.
ms.date: 11/06/2017
api_name:
- GetMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethod
helpviewer_keywords:
- GetMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5a405c5e245558e6b8d1b389bfc143faae4550a5
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54577599"
---
# <a name="getmethod-function"></a><span data-ttu-id="64360-103">GetMethod (función)</span><span class="sxs-lookup"><span data-stu-id="64360-103">GetMethod function</span></span>
<span data-ttu-id="64360-104">Recupera información sobre el método especificado.</span><span class="sxs-lookup"><span data-stu-id="64360-104">Retrieves information about the specified method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="64360-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="64360-105">Syntax</span></span>  
  
```  
HRESULT GetMethod (
   [in] int                vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszName,
   [in] LONG                lFlags,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
); 
```  

## <a name="parameters"></a><span data-ttu-id="64360-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="64360-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="64360-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="64360-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="64360-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="64360-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="64360-109">[in] El nombre del método.</span><span class="sxs-lookup"><span data-stu-id="64360-109">[in] The method name.</span></span> <span data-ttu-id="64360-110">Este parámetro no puede ser `null` y debe apuntar a una `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="64360-110">This parameter cannot be `null` and must point to a valid `LPCWSTR`.</span></span>

`lFlags`  
<span data-ttu-id="64360-111">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="64360-111">[in] Reserved.</span></span> <span data-ttu-id="64360-112">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="64360-112">This parameter must be 0.</span></span>

`ppInSignature`   
<span data-ttu-id="64360-113">[out] Un puntero a la dirección de un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia que describe el paramteers in al método.</span><span class="sxs-lookup"><span data-stu-id="64360-113">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the in paramteers to the method.</span></span> <span data-ttu-id="64360-114">Este parámetro se omite si se establece en `null`.</span><span class="sxs-lookup"><span data-stu-id="64360-114">This parameter is ignored if it is set to `null`.</span></span> 

`ppOutSignature`  
<span data-ttu-id="64360-115">[out] Un puntero a la dirección de un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia que se describe los parámetros out del método.</span><span class="sxs-lookup"><span data-stu-id="64360-115">[out] A pointer to the address of an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance that describes the out parameters to the method.</span></span> <span data-ttu-id="64360-116">Este parámetro se omite si se establece en `null`.</span><span class="sxs-lookup"><span data-stu-id="64360-116">This parameter is ignored if it is set to `null`.</span></span> 

## <a name="return-value"></a><span data-ttu-id="64360-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="64360-117">Return value</span></span>

<span data-ttu-id="64360-118">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="64360-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="64360-119">Constante</span><span class="sxs-lookup"><span data-stu-id="64360-119">Constant</span></span>  |<span data-ttu-id="64360-120">Valor</span><span class="sxs-lookup"><span data-stu-id="64360-120">Value</span></span>  |<span data-ttu-id="64360-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="64360-121">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="64360-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="64360-122">0x80041002</span></span> | <span data-ttu-id="64360-123">No se encontró la propiedad especificada.</span><span class="sxs-lookup"><span data-stu-id="64360-123">The specified property was not found.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="64360-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="64360-124">0x80041006</span></span> | <span data-ttu-id="64360-125">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="64360-125">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="64360-126">0</span><span class="sxs-lookup"><span data-stu-id="64360-126">0</span></span> | <span data-ttu-id="64360-127">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="64360-127">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="64360-128">Comentarios</span><span class="sxs-lookup"><span data-stu-id="64360-128">Remarks</span></span>

<span data-ttu-id="64360-129">Esta función contiene una llamada a la [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) método.</span><span class="sxs-lookup"><span data-stu-id="64360-129">This function wraps a call to the [IWbemClassObject::GetMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="64360-130">Administración de Windows se puede establecer el [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) puntero a `null` si el método no tiene ningún parámetro in.</span><span class="sxs-lookup"><span data-stu-id="64360-130">Windows Management can set the [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointer to `null` if the method has no in parameters.</span></span>

<span data-ttu-id="64360-131">En `ppInSignature` y `ppOutSignature` describen los parámetros, in y out, respectivamente, como propiedades en un `IWbemClassObject` instancia de la clase del sistema [_Parameters](/windows/desktop/WmiSdk/--parameters).</span><span class="sxs-lookup"><span data-stu-id="64360-131">In `ppInSignature` and `ppOutSignature` describe in and out parameters, respectively, as properties in a `IWbemClassObject` instance of the system class [_Parameters](/windows/desktop/WmiSdk/--parameters).</span></span> <span data-ttu-id="64360-132">Las propiedades de `ppInsignature` se denominan `Param` *n*, donde *n* es la posición del parámetro en la firma del método (como `Param1`, `Param2`, etcetera.).</span><span class="sxs-lookup"><span data-stu-id="64360-132">The properties in `ppInsignature` are named `Param`*n*, where *n* is the position of the parameter in the method signature (such as `Param1`, `Param2`, etc.).</span></span> <span data-ttu-id="64360-133">Las propiedades de `ppOutSignature` también se denominan `Param` *n*, y el valor devuelto se denomina `ReturnValue`.</span><span class="sxs-lookup"><span data-stu-id="64360-133">The properties in `ppOutSignature` are also named `Param`*n*, and the return value is named `ReturnValue`.</span></span> <span data-ttu-id="64360-134">Para obtener más información y un ejemplo, vea [IWbemClassObject::GetMethod método](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span><span class="sxs-lookup"><span data-stu-id="64360-134">For more information and an example, see [IWbemClassObject::GetMethod method](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod).</span></span>

## <a name="requirements"></a><span data-ttu-id="64360-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="64360-135">Requirements</span></span>  
<span data-ttu-id="64360-136">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="64360-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64360-137">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="64360-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="64360-138">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="64360-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64360-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="64360-139">See also</span></span>
- [<span data-ttu-id="64360-140">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="64360-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
