---
title: Función InheritsFrom (referencia de la API no administrada)
description: La función InheritsFrom determina si una clase o instancia deriva de una clase primaria concreta.
ms.date: 11/06/2017
api_name:
- InheritsFrom
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- InheritsFrom
helpviewer_keywords:
- InheritsFrom function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 6bda63377251e3a208dfb1620896535ccdf8ccd8
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127425"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="3ad1d-103">InheritsFrom función)</span><span class="sxs-lookup"><span data-stu-id="3ad1d-103">InheritsFrom function</span></span>
<span data-ttu-id="3ad1d-104">Determina si la clase o instancia actual deriva de una clase principal especificada.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="3ad1d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3ad1d-105">Syntax</span></span>  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="3ad1d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3ad1d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3ad1d-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="3ad1d-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="3ad1d-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="3ad1d-109">de Nombre de la clase.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-109">[in] The name of the class.</span></span> <span data-ttu-id="3ad1d-110">`wszAncestor` debe apuntar a un `LPCWSTR`válido.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="3ad1d-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3ad1d-111">Return value</span></span>

<span data-ttu-id="3ad1d-112">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="3ad1d-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3ad1d-113">Constante</span><span class="sxs-lookup"><span data-stu-id="3ad1d-113">Constant</span></span>  |<span data-ttu-id="3ad1d-114">Valor</span><span class="sxs-lookup"><span data-stu-id="3ad1d-114">Value</span></span>  |<span data-ttu-id="3ad1d-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="3ad1d-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="3ad1d-116">0</span><span class="sxs-lookup"><span data-stu-id="3ad1d-116">0</span></span> | <span data-ttu-id="3ad1d-117">El objeto actual hereda de `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="3ad1d-118">1</span><span class="sxs-lookup"><span data-stu-id="3ad1d-118">1</span></span> | <span data-ttu-id="3ad1d-119">El objeto actual no hereda de `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3ad1d-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3ad1d-120">0x80041008</span></span> | <span data-ttu-id="3ad1d-121">El valor de `wszAncestor` es `null`.</span><span class="sxs-lookup"><span data-stu-id="3ad1d-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="3ad1d-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3ad1d-122">Remarks</span></span>

<span data-ttu-id="3ad1d-123">Esta función contiene una llamada al método [IWbemClassObject:: InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) .</span><span class="sxs-lookup"><span data-stu-id="3ad1d-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="3ad1d-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3ad1d-124">Requirements</span></span>  
 <span data-ttu-id="3ad1d-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3ad1d-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3ad1d-126">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="3ad1d-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3ad1d-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3ad1d-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3ad1d-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="3ad1d-128">See also</span></span>

- [<span data-ttu-id="3ad1d-129">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="3ad1d-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
