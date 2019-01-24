---
title: EndMethodEnumeration (función) (referencia de API no administrada)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a098afe1702e9559a2784ea0716a0a61216e9fd4
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54535221"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="04c97-103">EndMethodEnumeration (función)</span><span class="sxs-lookup"><span data-stu-id="04c97-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="04c97-104">Finaliza una secuencia de enumeración que se inició con una llamada a la [BeginMethodEnumeration (función)](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="04c97-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="04c97-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="04c97-105">Syntax</span></span>  
  
```  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="04c97-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="04c97-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="04c97-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="04c97-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="04c97-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="04c97-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="04c97-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="04c97-109">Return value</span></span>

<span data-ttu-id="04c97-110">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="04c97-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="04c97-111">Constante</span><span class="sxs-lookup"><span data-stu-id="04c97-111">Constant</span></span>  |<span data-ttu-id="04c97-112">Valor</span><span class="sxs-lookup"><span data-stu-id="04c97-112">Value</span></span>  |<span data-ttu-id="04c97-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="04c97-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="04c97-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="04c97-114">0x8004101d</span></span> | <span data-ttu-id="04c97-115">Se ha producido un error interno.</span><span class="sxs-lookup"><span data-stu-id="04c97-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="04c97-116">0</span><span class="sxs-lookup"><span data-stu-id="04c97-116">0</span></span> | <span data-ttu-id="04c97-117">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="04c97-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="04c97-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="04c97-118">Remarks</span></span>

<span data-ttu-id="04c97-119">Esta función contiene una llamada a la [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) método.</span><span class="sxs-lookup"><span data-stu-id="04c97-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="04c97-120">El llamador comienza la secuencia de enumeración mediante [BeginMethodEnumeration (función)](beginmethodenumeration.md)y, a continuación, llama a la [NextMethod función](nextmethod.md )hasta que el método devuelve `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="04c97-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="04c97-121">El llamador, opcionalmente, finaliza la secuencia mediante una llamada a `EndMethodEnumeration`.</span><span class="sxs-lookup"><span data-stu-id="04c97-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="04c97-122">El llamador puede finalizar la enumeración al principio mediante una llamada a `EndMethodEnumeration` en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="04c97-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="04c97-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="04c97-123">Requirements</span></span>  
 <span data-ttu-id="04c97-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="04c97-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="04c97-125">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="04c97-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="04c97-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="04c97-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="04c97-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="04c97-127">See also</span></span>
- [<span data-ttu-id="04c97-128">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="04c97-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
