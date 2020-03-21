---
title: Función InheritsFrom (Referencia de API no administrada)
description: La función InheritsFrom determina si una clase o instancia deriva de una clase primaria determinada.
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
ms.openlocfilehash: c735c01c45beda8a1ba988a5c580e6b04ae46312
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79174945"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="da640-103">Función InheritsFrom</span><span class="sxs-lookup"><span data-stu-id="da640-103">InheritsFrom function</span></span>
<span data-ttu-id="da640-104">Determina si la clase o instancia actual deriva de una clase principal especificada.</span><span class="sxs-lookup"><span data-stu-id="da640-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="da640-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="da640-105">Syntax</span></span>  
  
```cpp
HRESULT InheritsFrom (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszAncestor
);
```  

## <a name="parameters"></a><span data-ttu-id="da640-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="da640-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="da640-107">[en] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="da640-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="da640-108">[en] Puntero a una instancia de [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="da640-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="da640-109">[en] El nombre de la clase.</span><span class="sxs-lookup"><span data-stu-id="da640-109">[in] The name of the class.</span></span> <span data-ttu-id="da640-110">`wszAncestor`debe apuntar a `LPCWSTR`un archivo .</span><span class="sxs-lookup"><span data-stu-id="da640-110">`wszAncestor` must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="da640-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="da640-111">Return value</span></span>

<span data-ttu-id="da640-112">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="da640-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="da640-113">Constante</span><span class="sxs-lookup"><span data-stu-id="da640-113">Constant</span></span>  |<span data-ttu-id="da640-114">Value</span><span class="sxs-lookup"><span data-stu-id="da640-114">Value</span></span>  |<span data-ttu-id="da640-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="da640-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="da640-116">0</span><span class="sxs-lookup"><span data-stu-id="da640-116">0</span></span> | <span data-ttu-id="da640-117">El objeto actual `wszAncestor`hereda de .</span><span class="sxs-lookup"><span data-stu-id="da640-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="da640-118">1</span><span class="sxs-lookup"><span data-stu-id="da640-118">1</span></span> | <span data-ttu-id="da640-119">El objeto actual no `wszAncestor`hereda de .</span><span class="sxs-lookup"><span data-stu-id="da640-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="da640-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="da640-120">0x80041008</span></span> | <span data-ttu-id="da640-121">`wszAncestor` es `null`.</span><span class="sxs-lookup"><span data-stu-id="da640-121">`wszAncestor` is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="da640-122">Observaciones</span><span class="sxs-lookup"><span data-stu-id="da640-122">Remarks</span></span>

<span data-ttu-id="da640-123">Esta función ajusta una llamada a la [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) método.</span><span class="sxs-lookup"><span data-stu-id="da640-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="da640-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="da640-124">Requirements</span></span>  
 <span data-ttu-id="da640-125">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="da640-125">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="da640-126">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="da640-126">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="da640-127">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="da640-127">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="da640-128">Consulte también</span><span class="sxs-lookup"><span data-stu-id="da640-128">See also</span></span>

- [<span data-ttu-id="da640-129">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="da640-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
