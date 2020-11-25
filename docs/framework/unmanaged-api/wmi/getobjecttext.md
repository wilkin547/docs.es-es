---
title: Función GetObjectText (referencia de la API no administrada)
description: La función GetObjectText devuelve una representación textual de un objeto en la sintaxis MOF.
ms.date: 11/06/2017
api_name:
- GetObjectText
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetObjectText
helpviewer_keywords:
- GetObjectText function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6ad2b29202222d594cc7976a13929002164314a7
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95718376"
---
# <a name="getobjecttext-function"></a><span data-ttu-id="f3ebd-103">Función GetObjectText</span><span class="sxs-lookup"><span data-stu-id="f3ebd-103">GetObjectText function</span></span>

<span data-ttu-id="f3ebd-104">Devuelve una representación textual del objeto en la sintaxis de Managed Object Format (MOF).</span><span class="sxs-lookup"><span data-stu-id="f3ebd-104">Returns a textual rendering of the object in the Managed Object Format (MOF) syntax.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="f3ebd-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="f3ebd-105">Syntax</span></span>  
  
```cpp  
HRESULT GetObjectText (
   [in] int                vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pstrObjectText
);
```  

## <a name="parameters"></a><span data-ttu-id="f3ebd-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="f3ebd-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="f3ebd-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="f3ebd-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="f3ebd-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="f3ebd-109">de Normalmente 0.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-109">[in] Normally 0.</span></span> <span data-ttu-id="f3ebd-110">Si `WBEM_FLAG_NO_FLAVORS` se especifica (o 0x1), los calificadores se incluyen sin información de propagación o de tipo.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-110">If `WBEM_FLAG_NO_FLAVORS` (or 0x1) is specified, qualifiers are included without propagation or flavor information.</span></span>

<span data-ttu-id="f3ebd-111">`pstrObjectText` enuncia Puntero a una `null` entrada.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-111">`pstrObjectText` [out] A pointer to a `null` on entry.</span></span> <span data-ttu-id="f3ebd-112">En la devolución, una recién asignada `BSTR` que contiene una representación de la sintaxis MOF del objeto.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-112">On return, a newly allocated `BSTR` that contains a MOF syntax rendering of the object.</span></span>  

## <a name="return-value"></a><span data-ttu-id="f3ebd-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="f3ebd-113">Return value</span></span>

<span data-ttu-id="f3ebd-114">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="f3ebd-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="f3ebd-115">Constante</span><span class="sxs-lookup"><span data-stu-id="f3ebd-115">Constant</span></span>  |<span data-ttu-id="f3ebd-116">Value</span><span class="sxs-lookup"><span data-stu-id="f3ebd-116">Value</span></span>  |<span data-ttu-id="f3ebd-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="f3ebd-117">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="f3ebd-118">0x80041001</span><span class="sxs-lookup"><span data-stu-id="f3ebd-118">0x80041001</span></span> | <span data-ttu-id="f3ebd-119">Se ha producido un error general.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-119">There has been a general failure.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="f3ebd-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="f3ebd-120">0x80041008</span></span> | <span data-ttu-id="f3ebd-121">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-121">A parameter is not valid.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="f3ebd-122">0x80041006</span><span class="sxs-lookup"><span data-stu-id="f3ebd-122">0x80041006</span></span> | <span data-ttu-id="f3ebd-123">Memoria insuficiente para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-123">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="f3ebd-124">0</span><span class="sxs-lookup"><span data-stu-id="f3ebd-124">0</span></span> | <span data-ttu-id="f3ebd-125">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-125">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="f3ebd-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="f3ebd-126">Remarks</span></span>

<span data-ttu-id="f3ebd-127">Esta función contiene una llamada al método [IWbemClassObject:: GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) .</span><span class="sxs-lookup"><span data-stu-id="f3ebd-127">This function wraps a call to the [IWbemClassObject::GetObjectText](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getobjecttext) method.</span></span>

<span data-ttu-id="f3ebd-128">El texto MOF devuelto no contiene toda la información sobre el objeto, sino solo información suficiente para que el compilador MOF pueda volver a crear el objeto original.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-128">The MOF text returned does not contain all the information about the object, but only enough information for the MOF compiler to be able to recreate the original object.</span></span> <span data-ttu-id="f3ebd-129">Por ejemplo, no se incluye ningún calificador propagado ni propiedades de clase primaria.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-129">For instance, no propagated qualifiers or parent class properties are included.</span></span>

<span data-ttu-id="f3ebd-130">El algoritmo siguiente se usa para reconstruir el texto de los parámetros de un método:</span><span class="sxs-lookup"><span data-stu-id="f3ebd-130">The following algorithm is used to reconstruct the text of the parameters of a method:</span></span>

1. <span data-ttu-id="f3ebd-131">Los parámetros se reordenan en el orden de sus valores de identificador.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-131">Parameters are resequenced in the order of their identifier values.</span></span>
1. <span data-ttu-id="f3ebd-132">Los parámetros que se especifican como `[in]` y `[out]` se combinan en un único parámetro.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-132">Parameters that are specified as `[in]` and `[out]` are combined into a single parameter.</span></span>

<span data-ttu-id="f3ebd-133">`pstrObjectText` debe ser un puntero a `null` cuando se llama a la función; no debe apuntar a una cadena que sea válida antes de la llamada al método, ya que el puntero no se desasignará.</span><span class="sxs-lookup"><span data-stu-id="f3ebd-133">`pstrObjectText` must be a pointer to a `null` when the function is called; it must not point to a string that is valid before the method call, because the pointer will not be deallocated.</span></span>

## <a name="requirements"></a><span data-ttu-id="f3ebd-134">Requisitos</span><span class="sxs-lookup"><span data-stu-id="f3ebd-134">Requirements</span></span>  

<span data-ttu-id="f3ebd-135">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="f3ebd-135">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f3ebd-136">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="f3ebd-136">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="f3ebd-137">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="f3ebd-137">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f3ebd-138">Consulte también</span><span class="sxs-lookup"><span data-stu-id="f3ebd-138">See also</span></span>

- [<span data-ttu-id="f3ebd-139">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="f3ebd-139">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
