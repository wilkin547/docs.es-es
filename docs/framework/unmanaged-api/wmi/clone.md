---
title: Función Clonar (Referencia de API no administrada)
description: La función Clone devuelve un nuevo objeto que es un clon completo del actual.
ms.date: 11/06/2017
api_name:
- Clone
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Clone
helpviewer_keywords:
- Clone function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: cb4951a1f289417482bfa1287028cc66349a5938
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176856"
---
# <a name="clone-function"></a><span data-ttu-id="8bd5f-103">Función Clone</span><span class="sxs-lookup"><span data-stu-id="8bd5f-103">Clone function</span></span>
<span data-ttu-id="8bd5f-104">Devuelve un objeto nuevo que es un clon completo del objeto actual.</span><span class="sxs-lookup"><span data-stu-id="8bd5f-104">Returns a new object that is a complete clone of the current object.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="8bd5f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8bd5f-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [out] IWbemClassObject**  ppCopy
);
```  

## <a name="parameters"></a><span data-ttu-id="8bd5f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8bd5f-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="8bd5f-107">[en] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="8bd5f-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="8bd5f-108">[en] Puntero a una instancia de [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="8bd5f-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="8bd5f-109">[fuera] Un nuevo objeto que es `ptr`una completa soledad de .</span><span class="sxs-lookup"><span data-stu-id="8bd5f-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="8bd5f-110">Este argumento `null` no puede ser si recibe la copia del objeto actual.</span><span class="sxs-lookup"><span data-stu-id="8bd5f-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="8bd5f-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8bd5f-111">Return value</span></span>

<span data-ttu-id="8bd5f-112">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="8bd5f-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8bd5f-113">Constante</span><span class="sxs-lookup"><span data-stu-id="8bd5f-113">Constant</span></span>  |<span data-ttu-id="8bd5f-114">Value</span><span class="sxs-lookup"><span data-stu-id="8bd5f-114">Value</span></span>  |<span data-ttu-id="8bd5f-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="8bd5f-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="8bd5f-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="8bd5f-116">0x80041001</span></span> | <span data-ttu-id="8bd5f-117">Ha habido un fracaso general.</span><span class="sxs-lookup"><span data-stu-id="8bd5f-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8bd5f-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8bd5f-118">0x80041008</span></span> | <span data-ttu-id="8bd5f-119">`null`se especificó como un parámetro, y no es legal en este uso.</span><span class="sxs-lookup"><span data-stu-id="8bd5f-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="8bd5f-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="8bd5f-120">0x80041006</span></span> | <span data-ttu-id="8bd5f-121">No hay suficiente memoria disponible para clonar el objeto.</span><span class="sxs-lookup"><span data-stu-id="8bd5f-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="8bd5f-122">0</span><span class="sxs-lookup"><span data-stu-id="8bd5f-122">0</span></span> | <span data-ttu-id="8bd5f-123">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="8bd5f-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="8bd5f-124">Observaciones</span><span class="sxs-lookup"><span data-stu-id="8bd5f-124">Remarks</span></span>

<span data-ttu-id="8bd5f-125">Esta función ajusta una llamada a la [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) método.</span><span class="sxs-lookup"><span data-stu-id="8bd5f-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="8bd5f-126">El objeto clonado es un objeto COM que tiene un recuento de referencias de 1.</span><span class="sxs-lookup"><span data-stu-id="8bd5f-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="8bd5f-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8bd5f-127">Requirements</span></span>  
 <span data-ttu-id="8bd5f-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8bd5f-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8bd5f-129">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8bd5f-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="8bd5f-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8bd5f-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8bd5f-131">Consulte también</span><span class="sxs-lookup"><span data-stu-id="8bd5f-131">See also</span></span>

- [<span data-ttu-id="8bd5f-132">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="8bd5f-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
