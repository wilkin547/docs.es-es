---
title: Función EndMethodEnumeration (referencia de la API no administrada)
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
ms.openlocfilehash: cdcf49bd748a423b1cebfba88644aa961f1c7b65
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799343"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="54045-103">Función EndMethodEnumeration</span><span class="sxs-lookup"><span data-stu-id="54045-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="54045-104">Finaliza una secuencia de enumeración iniciada con una llamada a la [función BeginMethodEnumeration](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="54045-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="54045-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="54045-105">Syntax</span></span>  
  
```cpp  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="54045-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="54045-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="54045-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="54045-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="54045-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="54045-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="54045-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="54045-109">Return value</span></span>

<span data-ttu-id="54045-110">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="54045-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="54045-111">Constante</span><span class="sxs-lookup"><span data-stu-id="54045-111">Constant</span></span>  |<span data-ttu-id="54045-112">Valor</span><span class="sxs-lookup"><span data-stu-id="54045-112">Value</span></span>  |<span data-ttu-id="54045-113">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="54045-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="54045-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="54045-114">0x8004101d</span></span> | <span data-ttu-id="54045-115">Se ha producido un error interno.</span><span class="sxs-lookup"><span data-stu-id="54045-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="54045-116">0</span><span class="sxs-lookup"><span data-stu-id="54045-116">0</span></span> | <span data-ttu-id="54045-117">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="54045-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="54045-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="54045-118">Remarks</span></span>

<span data-ttu-id="54045-119">Esta función contiene una llamada al método [IWbemClassObject:: EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) .</span><span class="sxs-lookup"><span data-stu-id="54045-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="54045-120">El autor de la llamada comienza la secuencia de enumeración mediante la [función BeginMethodEnumeration](beginmethodenumeration.md)y, a continuación, llama `WBEM_S_NO_MORE_DATA`a la [función NextMethod](nextmethod.md )hasta que el método devuelve.</span><span class="sxs-lookup"><span data-stu-id="54045-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="54045-121">Opcionalmente, el llamador finaliza la secuencia mediante `EndMethodEnumeration`una llamada a.</span><span class="sxs-lookup"><span data-stu-id="54045-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="54045-122">El autor de la llamada puede finalizar la enumeración `EndMethodEnumeration` al principio llamando a en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="54045-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="54045-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="54045-123">Requirements</span></span>  
 <span data-ttu-id="54045-124">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="54045-124">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="54045-125">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="54045-125">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="54045-126">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="54045-126">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="54045-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="54045-127">See also</span></span>

- [<span data-ttu-id="54045-128">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="54045-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
