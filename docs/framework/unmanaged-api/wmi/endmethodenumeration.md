---
title: Función EndMethodEnumeration (Referencia de API no administrada)
description: La función EndMethodEnumeration finaliza una secuencia de enumeración de método.
ms.date: 11/06/2017
api_name:
- EndMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndMethodEnumeration
helpviewer_keywords:
- EndMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 63667d0668f905ded2aedd961be0d1831faf838c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175010"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="b9712-103">Función EndMethodEnumeration</span><span class="sxs-lookup"><span data-stu-id="b9712-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="b9712-104">Termina una secuencia de enumeración iniciada con una llamada a la [función BeginMethodEnumeration](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="b9712-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="b9712-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="b9712-105">Syntax</span></span>  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr
);
```  

## <a name="parameters"></a><span data-ttu-id="b9712-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="b9712-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="b9712-107">[en] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="b9712-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="b9712-108">[en] Puntero a una instancia de [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="b9712-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="b9712-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="b9712-109">Return value</span></span>

<span data-ttu-id="b9712-110">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="b9712-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="b9712-111">Constante</span><span class="sxs-lookup"><span data-stu-id="b9712-111">Constant</span></span>  |<span data-ttu-id="b9712-112">Value</span><span class="sxs-lookup"><span data-stu-id="b9712-112">Value</span></span>  |<span data-ttu-id="b9712-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="b9712-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="b9712-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="b9712-114">0x8004101d</span></span> | <span data-ttu-id="b9712-115">Error interno.</span><span class="sxs-lookup"><span data-stu-id="b9712-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="b9712-116">0</span><span class="sxs-lookup"><span data-stu-id="b9712-116">0</span></span> | <span data-ttu-id="b9712-117">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="b9712-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="b9712-118">Observaciones</span><span class="sxs-lookup"><span data-stu-id="b9712-118">Remarks</span></span>

<span data-ttu-id="b9712-119">Esta función ajusta una llamada a la [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) método.</span><span class="sxs-lookup"><span data-stu-id="b9712-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="b9712-120">El llamador comienza la secuencia de enumeración mediante [beginMethodEnumeration función](beginmethodenumeration.md)y, a continuación, llama a la [NextMethod función](nextmethod.md )hasta que el método devuelve `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="b9712-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="b9712-121">El autor de la llamada `EndMethodEnumeration`finaliza opcionalmente la secuencia llamando a .</span><span class="sxs-lookup"><span data-stu-id="b9712-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="b9712-122">El llamador puede terminar `EndMethodEnumeration` la enumeración antes de tiempo llamando en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="b9712-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="b9712-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="b9712-123">Requirements</span></span>  
 <span data-ttu-id="b9712-124">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="b9712-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b9712-125">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="b9712-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="b9712-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="b9712-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b9712-127">Consulte también</span><span class="sxs-lookup"><span data-stu-id="b9712-127">See also</span></span>

- [<span data-ttu-id="b9712-128">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="b9712-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
