---
title: Función InheritsFrom (referencia de API no administrada)
description: La función InheritsFrom determina si una instancia o clase se deriva de una clase primaria determinada.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0d2af1b41f47a3906c0e573c104847aa3ff36cf8
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59158436"
---
# <a name="inheritsfrom-function"></a><span data-ttu-id="4145e-103">Función InheritsFrom</span><span class="sxs-lookup"><span data-stu-id="4145e-103">InheritsFrom function</span></span>
<span data-ttu-id="4145e-104">Determina si la clase o instancia actual deriva de una clase principal especificada.</span><span class="sxs-lookup"><span data-stu-id="4145e-104">Determines whether the current class or instance derives from a specified parent class.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="4145e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4145e-105">Syntax</span></span>  
  
```
HRESULT InheritsFrom (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszAncestor 
); 
```  

## <a name="parameters"></a><span data-ttu-id="4145e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4145e-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="4145e-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="4145e-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="4145e-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="4145e-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszAncestor`  
<span data-ttu-id="4145e-109">[in] El nombre de la clase.</span><span class="sxs-lookup"><span data-stu-id="4145e-109">[in] The name of the class.</span></span> `wszAncestor` <span data-ttu-id="4145e-110">debe apuntar a una `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="4145e-110">must point to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="4145e-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4145e-111">Return value</span></span>

<span data-ttu-id="4145e-112">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="4145e-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4145e-113">Constante</span><span class="sxs-lookup"><span data-stu-id="4145e-113">Constant</span></span>  |<span data-ttu-id="4145e-114">Valor</span><span class="sxs-lookup"><span data-stu-id="4145e-114">Value</span></span>  |<span data-ttu-id="4145e-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="4145e-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_S_NO_ERROR` | <span data-ttu-id="4145e-116">0</span><span class="sxs-lookup"><span data-stu-id="4145e-116">0</span></span> | <span data-ttu-id="4145e-117">El objeto actual se hereda de `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="4145e-117">The current object inherits from `wszAncestor`.</span></span>  |
| `WBEM_S_FALSE` | <span data-ttu-id="4145e-118">1</span><span class="sxs-lookup"><span data-stu-id="4145e-118">1</span></span> | <span data-ttu-id="4145e-119">El objeto actual no hereda de `wszAncestor`.</span><span class="sxs-lookup"><span data-stu-id="4145e-119">The current object does not inherit from `wszAncestor`.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="4145e-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="4145e-120">0x80041008</span></span> | `wszAncestor` <span data-ttu-id="4145e-121">es `null`.</span><span class="sxs-lookup"><span data-stu-id="4145e-121">is `null`.</span></span> |
  
## <a name="remarks"></a><span data-ttu-id="4145e-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="4145e-122">Remarks</span></span>

<span data-ttu-id="4145e-123">Esta función contiene una llamada a la [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) método.</span><span class="sxs-lookup"><span data-stu-id="4145e-123">This function wraps a call to the [IWbemClassObject::InheritsFrom](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-inheritsfrom) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="4145e-124">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4145e-124">Requirements</span></span>  
 <span data-ttu-id="4145e-125">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4145e-125">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4145e-126">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="4145e-126">**Header:** WMINet_Utils.idl</span></span>  
  
 **<span data-ttu-id="4145e-127">Versiones de .NET Framework:</span><span class="sxs-lookup"><span data-stu-id="4145e-127">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a><span data-ttu-id="4145e-128">Vea también</span><span class="sxs-lookup"><span data-stu-id="4145e-128">See also</span></span>

- [<span data-ttu-id="4145e-129">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="4145e-129">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
