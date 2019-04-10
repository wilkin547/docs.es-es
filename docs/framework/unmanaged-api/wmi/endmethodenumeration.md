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
ms.openlocfilehash: e7f29c365e9f6ba85f85ceb232f7af89446af2a1
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59213056"
---
# <a name="endmethodenumeration-function"></a><span data-ttu-id="534f6-103">Función EndMethodEnumeration</span><span class="sxs-lookup"><span data-stu-id="534f6-103">EndMethodEnumeration function</span></span>
<span data-ttu-id="534f6-104">Finaliza una secuencia de enumeración que se inició con una llamada a la [BeginMethodEnumeration (función)](beginmethodenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="534f6-104">Terminates an enumeration sequence started with a call to the [BeginMethodEnumeration function](beginmethodenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="534f6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="534f6-105">Syntax</span></span>  
  
```  
HRESULT EndMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="534f6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="534f6-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="534f6-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="534f6-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="534f6-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="534f6-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

## <a name="return-value"></a><span data-ttu-id="534f6-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="534f6-109">Return value</span></span>

<span data-ttu-id="534f6-110">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="534f6-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="534f6-111">Constante</span><span class="sxs-lookup"><span data-stu-id="534f6-111">Constant</span></span>  |<span data-ttu-id="534f6-112">Valor</span><span class="sxs-lookup"><span data-stu-id="534f6-112">Value</span></span>  |<span data-ttu-id="534f6-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="534f6-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_UNEXPECTED` | <span data-ttu-id="534f6-114">0x8004101d</span><span class="sxs-lookup"><span data-stu-id="534f6-114">0x8004101d</span></span> | <span data-ttu-id="534f6-115">Se ha producido un error interno.</span><span class="sxs-lookup"><span data-stu-id="534f6-115">An internal error occurred.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="534f6-116">0</span><span class="sxs-lookup"><span data-stu-id="534f6-116">0</span></span> | <span data-ttu-id="534f6-117">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="534f6-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="534f6-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="534f6-118">Remarks</span></span>

<span data-ttu-id="534f6-119">Esta función contiene una llamada a la [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) método.</span><span class="sxs-lookup"><span data-stu-id="534f6-119">This function wraps a call to the [IWbemClassObject::EndMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-endmethodenumeration) method.</span></span>

<span data-ttu-id="534f6-120">El llamador comienza la secuencia de enumeración mediante [BeginMethodEnumeration (función)](beginmethodenumeration.md)y, a continuación, llama a la [NextMethod función](nextmethod.md )hasta que el método devuelve `WBEM_S_NO_MORE_DATA`.</span><span class="sxs-lookup"><span data-stu-id="534f6-120">The caller begins the enumeration sequence using [BeginMethodEnumeration function](beginmethodenumeration.md), and then calls the [NextMethod function](nextmethod.md )until the method  returns `WBEM_S_NO_MORE_DATA`.</span></span> <span data-ttu-id="534f6-121">El llamador, opcionalmente, finaliza la secuencia mediante una llamada a `EndMethodEnumeration`.</span><span class="sxs-lookup"><span data-stu-id="534f6-121">The caller optionally finishes the sequence by calling `EndMethodEnumeration`.</span></span> <span data-ttu-id="534f6-122">El llamador puede finalizar la enumeración al principio mediante una llamada a `EndMethodEnumeration` en cualquier momento.</span><span class="sxs-lookup"><span data-stu-id="534f6-122">The caller may terminate the enumeration early by calling `EndMethodEnumeration` at any time.</span></span>

## <a name="requirements"></a><span data-ttu-id="534f6-123">Requisitos</span><span class="sxs-lookup"><span data-stu-id="534f6-123">Requirements</span></span>  
 <span data-ttu-id="534f6-124">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="534f6-124">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="534f6-125">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="534f6-125">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="534f6-126">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="534f6-126">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="534f6-127">Vea también</span><span class="sxs-lookup"><span data-stu-id="534f6-127">See also</span></span>

- [<span data-ttu-id="534f6-128">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="534f6-128">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
