---
title: Función NextMethod (referencia de la API no administrada)
description: La función NextMethod recupera el método siguiente en una enumeración.
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
ms.openlocfilehash: 1c20fe5b4a081bd41f51365a36ab5f8f8cfb71ed
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127358"
---
# <a name="nextmethod-function"></a><span data-ttu-id="47e66-103">NextMethod función)</span><span class="sxs-lookup"><span data-stu-id="47e66-103">NextMethod function</span></span>
<span data-ttu-id="47e66-104">Recupera el método siguiente en una enumeración que comienza con una llamada a [BeginMethodEnumeration](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="47e66-104">Retrieves the next method in an enumeration that begins with a call to [BeginMethodEnumeration](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="47e66-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="47e66-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="47e66-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="47e66-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="47e66-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="47e66-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="47e66-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="47e66-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="47e66-109">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="47e66-109">[in] Reserved.</span></span> <span data-ttu-id="47e66-110">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="47e66-110">This parameter must be 0.</span></span>

`pName`  
<span data-ttu-id="47e66-111">enuncia Puntero que apunta a `null` antes de la llamada.</span><span class="sxs-lookup"><span data-stu-id="47e66-111">[out] A pointer that points to `null` prior to the call.</span></span> <span data-ttu-id="47e66-112">Cuando la función devuelve, la dirección de un nuevo `BSTR` que contiene el nombre del método.</span><span class="sxs-lookup"><span data-stu-id="47e66-112">When the function returns, the address of a new `BSTR` that contains the method name.</span></span> 

`ppSignatureIn`  
<span data-ttu-id="47e66-113">enuncia Puntero que recibe un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que contiene los parámetros de `in` para el método.</span><span class="sxs-lookup"><span data-stu-id="47e66-113">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `in` parameters for the method.</span></span> 

`ppSignatureOut`  
<span data-ttu-id="47e66-114">enuncia Puntero que recibe un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que contiene los parámetros de `out` para el método.</span><span class="sxs-lookup"><span data-stu-id="47e66-114">[out] A pointer that receives a pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) that contains the `out` parameters for the method.</span></span> 

## <a name="return-value"></a><span data-ttu-id="47e66-115">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="47e66-115">Return value</span></span>

<span data-ttu-id="47e66-116">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="47e66-116">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="47e66-117">Constante</span><span class="sxs-lookup"><span data-stu-id="47e66-117">Constant</span></span>  |<span data-ttu-id="47e66-118">Valor</span><span class="sxs-lookup"><span data-stu-id="47e66-118">Value</span></span>  |<span data-ttu-id="47e66-119">Descripción</span><span class="sxs-lookup"><span data-stu-id="47e66-119">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_UNEXPECTED` | <span data-ttu-id="47e66-120">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="47e66-120">0x8004101d</span></span> | <span data-ttu-id="47e66-121">No había ninguna llamada a la función [`BeginEnumeration`](beginenumeration.md) .</span><span class="sxs-lookup"><span data-stu-id="47e66-121">There was no call to the [`BeginEnumeration`](beginenumeration.md) function.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="47e66-122">0</span><span class="sxs-lookup"><span data-stu-id="47e66-122">0</span></span> | <span data-ttu-id="47e66-123">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="47e66-123">The function call was successful.</span></span>  |
| `WBEM_S_NO_MORE_DATA` | <span data-ttu-id="47e66-124">0x40005</span><span class="sxs-lookup"><span data-stu-id="47e66-124">0x40005</span></span> | <span data-ttu-id="47e66-125">No hay más propiedades en la enumeración.</span><span class="sxs-lookup"><span data-stu-id="47e66-125">There are no more properties in the enumeration.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="47e66-126">Comentarios</span><span class="sxs-lookup"><span data-stu-id="47e66-126">Remarks</span></span>

<span data-ttu-id="47e66-127">Esta función contiene una llamada al método [IWbemClassObject:: NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .</span><span class="sxs-lookup"><span data-stu-id="47e66-127">This function wraps a call to the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

<span data-ttu-id="47e66-128">El autor de la llamada comienza la secuencia de enumeración mediante una llamada a la función [BeginMethodEnumeration](beginmethodenumeration.md) y, a continuación, llama a la función [NextMethod] hasta que la función devuelve `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="47e66-128">The caller begins the enumeration sequence by calling the [BeginMethodEnumeration](beginmethodenumeration.md) function, and then calls the [NextMethod] function until the function returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="47e66-129">Opcionalmente, el autor de la llamada finaliza la secuencia llamando a [EndMethodEnumeration](endmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="47e66-129">Optionally, the caller finishes the sequence by calling [EndMethodEnumeration](endmethodenumeration.md).</span></span> <span data-ttu-id="47e66-130">El autor de la llamada puede finalizar la enumeración pronto llamando a [EndMethodEnumeration](endmethodenumeration.md) en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="47e66-130">The caller may terminate the enumeration early by calling [EndMethodEnumeration](endmethodenumeration.md) at any time.</span></span>

## <a name="example"></a><span data-ttu-id="47e66-131">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="47e66-131">Example</span></span>

<span data-ttu-id="47e66-132">Para obtener C++ un ejemplo, vea el método [IWbemClassObject:: NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) .</span><span class="sxs-lookup"><span data-stu-id="47e66-132">For a C++ example, see the [IWbemClassObject::NextMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-nextmethod) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="47e66-133">Requisitos</span><span class="sxs-lookup"><span data-stu-id="47e66-133">Requirements</span></span>  
 <span data-ttu-id="47e66-134">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="47e66-134">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="47e66-135">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="47e66-135">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="47e66-136">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="47e66-136">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47e66-137">Vea también</span><span class="sxs-lookup"><span data-stu-id="47e66-137">See also</span></span>

- [<span data-ttu-id="47e66-138">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="47e66-138">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
