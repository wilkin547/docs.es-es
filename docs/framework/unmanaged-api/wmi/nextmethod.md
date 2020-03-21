---
title: Función NextMethod (Referencia de API no administrada)
description: La función NextMethod recupera el siguiente método de una enumeración.
ms.date: 11/06/2017
api_name:
- NextMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- NextMethod
helpviewer_keywords:
- NextMethod function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 36acd6135110a8865bd8efdda628c352c01b4f26
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174932"
---
# <a name="nextmethod-function"></a><span data-ttu-id="346e0-103">Función NextMethod</span><span class="sxs-lookup"><span data-stu-id="346e0-103">NextMethod function</span></span>
<span data-ttu-id="346e0-104">Recupera el siguiente método de una enumeración que comienza con una llamada a [BeginMethodEnumeration](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="346e0-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="346e0-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="346e0-105">Syntax</span></span>  
  
```cpp  
HRESULT NextMethod (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LONG                lFlags,
   [out] BSTR*              pName,
   [out] IWbemClassObject** ppInSignature,
   [out] IWbemClassObject** ppOutSignature
);
```  

## <a name="parameters"></a><span data-ttu-id="346e0-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="346e0-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="346e0-107">[en] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="346e0-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="346e0-108">[en] Puntero a una instancia de [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="346e0-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="346e0-109">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="346e0-109">[in] Reserved.</span></span> <span data-ttu-id="346e0-110">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="346e0-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="346e0-111">[fuera] Puntero que apunta `null` a antes de la llamada.</span><span class="sxs-lookup"><span data-stu-id="346e0-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="346e0-112">Cuando se devuelve la función, la dirección de un nuevo `BSTR` que contiene el nombre del método.</span><span class="sxs-lookup"><span data-stu-id="346e0-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span>

`ppSignatureIn`  
<span data-ttu-id="346e0-113">[fuera] Puntero que recibe un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que contiene los `in` parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="346e0-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span>

`ppSignatureOut`  
<span data-ttu-id="346e0-114">[fuera] Puntero que recibe un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que contiene los `out` parámetros del método.</span><span class="sxs-lookup"><span data-stu-id="346e0-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="346e0-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="346e0-115">Return value</span></span>

<span data-ttu-id="346e0-116">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="346e0-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="346e0-117">Constante</span><span class="sxs-lookup"><span data-stu-id="346e0-117">Constant</span></span>  |<span data-ttu-id="346e0-118">Value</span><span class="sxs-lookup"><span data-stu-id="346e0-118">Value</span></span>  |<span data-ttu-id="346e0-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="346e0-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="346e0-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="346e0-120">0x8004101d</span></span> | <span data-ttu-id="346e0-121">No hubo ninguna [`BeginEnumeration`](beginenumeration.md) llamada a la función.</span><span class="sxs-lookup"><span data-stu-id="346e0-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="346e0-122">0</span><span class="sxs-lookup"><span data-stu-id="346e0-122">0</span></span> | <span data-ttu-id="346e0-123">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="346e0-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="346e0-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="346e0-124">0x40005</span></span> | <span data-ttu-id="346e0-125">No hay más propiedades en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="346e0-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="346e0-126">Observaciones</span><span class="sxs-lookup"><span data-stu-id="346e0-126">Remarks</span></span>

<span data-ttu-id="346e0-127">Esta función ajusta una llamada a la [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) método.</span><span class="sxs-lookup"><span data-stu-id="346e0-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="346e0-128">El llamador comienza la secuencia de enumeración llamando a la función [BeginMethodEnumeration](beginmethodenumeration.md) y, a continuación, llama a la función [NextMethod] hasta que la función devuelve `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="346e0-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="346e0-129">Opcionalmente, el llamador finaliza la secuencia llamando a [EndMethodEnumeration](endmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="346e0-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="346e0-130">El llamador puede terminar la enumeración antes de tiempo llamando a [EndMethodEnumeration](endmethodenumeration.md) en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="346e0-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="346e0-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="346e0-131">Example</span></span>

<span data-ttu-id="346e0-132">Para obtener un ejemplo de C++, vea el [Método IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .</span><span class="sxs-lookup"><span data-stu-id="346e0-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="346e0-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="346e0-133">Requirements</span></span>  
 <span data-ttu-id="346e0-134">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="346e0-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="346e0-135">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="346e0-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="346e0-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="346e0-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="346e0-137">Consulte también</span><span class="sxs-lookup"><span data-stu-id="346e0-137">See also</span></span>

- [<span data-ttu-id="346e0-138">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="346e0-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
