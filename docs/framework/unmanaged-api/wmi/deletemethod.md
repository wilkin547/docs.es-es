---
title: DeleteMethod (función) (referencia de API no administrada)
description: La función DeleteMethod elimina el método especificado de una definición de clase CIM.
ms.date: 11/06/2017
api_name:
- DeleteMethod
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- DeleteMethod
helpviewer_keywords:
- DeleteMethod function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5996ce41c80cb54c4fcb9104c2993c85bcc2b466
ms.sourcegitcommit: 76a304c79a32aa13889ebcf4b9789a4542b48e3e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/13/2018
ms.locfileid: "45510239"
---
# <a name="deletemethod-function"></a><span data-ttu-id="58781-103">DeleteMethod (función)</span><span class="sxs-lookup"><span data-stu-id="58781-103">DeleteMethod function</span></span>
<span data-ttu-id="58781-104">Elimina el método especificado de una definición de clase CIM.</span><span class="sxs-lookup"><span data-stu-id="58781-104">Deletes the specified method from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="58781-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="58781-105">Syntax</span></span>  
  
```  
HRESULT Delete (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LPCWSTR           wszName 
); 
```  

## <a name="parameters"></a><span data-ttu-id="58781-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="58781-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="58781-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="58781-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="58781-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="58781-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`  
<span data-ttu-id="58781-109">[in] El nombre del método que se va a quitar de la tabla de la clase.</span><span class="sxs-lookup"><span data-stu-id="58781-109">[in] The name of the method to remove from the class table.</span></span> <span data-ttu-id="58781-110">`wszName` debe ser un puntero a una `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="58781-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="58781-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="58781-111">Return value</span></span>

<span data-ttu-id="58781-112">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="58781-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="58781-113">Constante</span><span class="sxs-lookup"><span data-stu-id="58781-113">Constant</span></span>  |<span data-ttu-id="58781-114">Valor</span><span class="sxs-lookup"><span data-stu-id="58781-114">Value</span></span>  |<span data-ttu-id="58781-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="58781-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="58781-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="58781-116">0x80041002</span></span> | <span data-ttu-id="58781-117">El método especificado no existe.</span><span class="sxs-lookup"><span data-stu-id="58781-117">The specified method does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="58781-118">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="58781-118">0x80041006</span></span> | <span data-ttu-id="58781-119">No hay memoria suficiente para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="58781-119">There is not enough memory to complete the operation.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="58781-120">0</span><span class="sxs-lookup"><span data-stu-id="58781-120">0</span></span> | <span data-ttu-id="58781-121">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="58781-121">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="58781-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="58781-122">Remarks</span></span>

<span data-ttu-id="58781-123">Esta función contiene una llamada a la [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) método.</span><span class="sxs-lookup"><span data-stu-id="58781-123">This function wraps a call to the [IWbemClassObject::DeleteMethod](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-deletemethod) method.</span></span>

<span data-ttu-id="58781-124">No se admite la eliminación de método para [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) punteros que señalan a las instancias CIM.</span><span class="sxs-lookup"><span data-stu-id="58781-124">Method deletion is not supported for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

## <a name="requirements"></a><span data-ttu-id="58781-125">Requisitos</span><span class="sxs-lookup"><span data-stu-id="58781-125">Requirements</span></span>  
 <span data-ttu-id="58781-126">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="58781-126">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="58781-127">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="58781-127">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="58781-128">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="58781-128">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="58781-129">Vea también</span><span class="sxs-lookup"><span data-stu-id="58781-129">See also</span></span>  
[<span data-ttu-id="58781-130">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="58781-130">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
