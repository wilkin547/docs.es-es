---
title: EndEnumeration (función) (referencia de API no administrada)
description: La función EndEnumeration finaliza una enumeración.
ms.date: 11/06/2017
api_name:
- EndEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- EndEnumeration
helpviewer_keywords:
- EndEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 33c73e58be39a7f1ffa9300947c3ee552231adab
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43786354"
---
# <a name="endenumeration-function"></a><span data-ttu-id="905e5-103">EndEnumeration (función)</span><span class="sxs-lookup"><span data-stu-id="905e5-103">EndEnumeration function</span></span>
<span data-ttu-id="905e5-104">Finaliza una secuencia de enumeración que se inició con una llamada a la [BeginEnumeration (función)](beginenumeration.md).</span><span class="sxs-lookup"><span data-stu-id="905e5-104">Terminates an enumeration sequence started with a call to the [BeginEnumeration function](beginenumeration.md).</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="905e5-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="905e5-105">Syntax</span></span>  
  
```  
HRESULT EndEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr 
); 
```  

## <a name="parameters"></a><span data-ttu-id="905e5-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="905e5-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="905e5-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="905e5-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="905e5-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="905e5-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>


## <a name="return-value"></a><span data-ttu-id="905e5-109">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="905e5-109">Return value</span></span>

<span data-ttu-id="905e5-110">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="905e5-110">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="905e5-111">Constante</span><span class="sxs-lookup"><span data-stu-id="905e5-111">Constant</span></span>  |<span data-ttu-id="905e5-112">Valor</span><span class="sxs-lookup"><span data-stu-id="905e5-112">Value</span></span>  |<span data-ttu-id="905e5-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="905e5-113">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="905e5-114">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="905e5-114">0x80041001</span></span> | <span data-ttu-id="905e5-115">Ha habido un error general.</span><span class="sxs-lookup"><span data-stu-id="905e5-115">There has been a general failure.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="905e5-116">0</span><span class="sxs-lookup"><span data-stu-id="905e5-116">0</span></span> | <span data-ttu-id="905e5-117">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="905e5-117">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="905e5-118">Comentarios</span><span class="sxs-lookup"><span data-stu-id="905e5-118">Remarks</span></span>

<span data-ttu-id="905e5-119">Esta función contiene una llamada a la [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) método.</span><span class="sxs-lookup"><span data-stu-id="905e5-119">This function wraps a call to the [IWbemClassObject::EndEnumeration](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) method.</span></span>

<span data-ttu-id="905e5-120">Una llamada a la `EndEnumeration` función no es necesaria, pero se recomienda porque lo libera los recursos asociados a la enumeración.</span><span class="sxs-lookup"><span data-stu-id="905e5-120">A call to the `EndEnumeration` function is not required, but it is recommended because it releases resources associated with the enumeration.</span></span> <span data-ttu-id="905e5-121">Sin embargo, los recursos se desasignan automáticamente cuando se inicia la enumeración siguiente o se libera el objeto.</span><span class="sxs-lookup"><span data-stu-id="905e5-121">However, the resoruces are deallocated automatically when the next enumeration is started or the object is released.</span></span>

## <a name="requirements"></a><span data-ttu-id="905e5-122">Requisitos</span><span class="sxs-lookup"><span data-stu-id="905e5-122">Requirements</span></span>  
 <span data-ttu-id="905e5-123">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="905e5-123">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="905e5-124">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="905e5-124">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="905e5-125">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="905e5-125">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="905e5-126">Vea también</span><span class="sxs-lookup"><span data-stu-id="905e5-126">See also</span></span>  
[<span data-ttu-id="905e5-127">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="905e5-127">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
