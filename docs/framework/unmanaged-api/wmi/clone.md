---
title: Función Clone (referencia de la API no administrada)
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
ms.openlocfilehash: c8e7781a3efe7679ef2e05747862911db88bcc5f
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141616"
---
# <a name="clone-function"></a><span data-ttu-id="21156-103">Función Clone</span><span class="sxs-lookup"><span data-stu-id="21156-103">Clone function</span></span>
<span data-ttu-id="21156-104">Devuelve un objeto nuevo que es un clon completo del objeto actual.</span><span class="sxs-lookup"><span data-stu-id="21156-104">Returns a new object that is a complete clone of the current object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="21156-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="21156-105">Syntax</span></span>  
  
```cpp  
HRESULT Clone (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [out] IWbemClassObject**  ppCopy
); 
```  

## <a name="parameters"></a><span data-ttu-id="21156-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="21156-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="21156-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="21156-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="21156-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="21156-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppCopy`  
<span data-ttu-id="21156-109">enuncia Un nuevo objeto que es una función completa de `ptr`.</span><span class="sxs-lookup"><span data-stu-id="21156-109">[out] A new object that is a complete lone of `ptr`.</span></span> <span data-ttu-id="21156-110">No se puede `null` este argumento si recibe la copia del objeto actual.</span><span class="sxs-lookup"><span data-stu-id="21156-110">This argument cannot be `null` if it receives the copy of the current object.</span></span>

## <a name="return-value"></a><span data-ttu-id="21156-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="21156-111">Return value</span></span>

<span data-ttu-id="21156-112">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="21156-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="21156-113">Constante</span><span class="sxs-lookup"><span data-stu-id="21156-113">Constant</span></span>  |<span data-ttu-id="21156-114">Valor</span><span class="sxs-lookup"><span data-stu-id="21156-114">Value</span></span>  |<span data-ttu-id="21156-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="21156-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="21156-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="21156-116">0x80041001</span></span> | <span data-ttu-id="21156-117">Se ha producido un error general.</span><span class="sxs-lookup"><span data-stu-id="21156-117">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="21156-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="21156-118">0x80041008</span></span> | <span data-ttu-id="21156-119">`null` se especificó como parámetro y no es válido en este uso.</span><span class="sxs-lookup"><span data-stu-id="21156-119">`null` was specified as a parameter, and it is not legal in this usage.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="21156-120">0x80041006</span><span class="sxs-lookup"><span data-stu-id="21156-120">0x80041006</span></span> | <span data-ttu-id="21156-121">No hay suficiente memoria disponible para clonar el objeto.</span><span class="sxs-lookup"><span data-stu-id="21156-121">Not enough memory is available to clone the object.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="21156-122">0</span><span class="sxs-lookup"><span data-stu-id="21156-122">0</span></span> | <span data-ttu-id="21156-123">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="21156-123">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="21156-124">Comentarios</span><span class="sxs-lookup"><span data-stu-id="21156-124">Remarks</span></span>

<span data-ttu-id="21156-125">Esta función contiene una llamada al método [IWbemClassObject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) .</span><span class="sxs-lookup"><span data-stu-id="21156-125">This function wraps a call to the [IWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="21156-126">El objeto clonado es un objeto COM que tiene un recuento de referencias de 1.</span><span class="sxs-lookup"><span data-stu-id="21156-126">The cloned object is a COM object that has a reference count of 1.</span></span>

## <a name="requirements"></a><span data-ttu-id="21156-127">Requisitos</span><span class="sxs-lookup"><span data-stu-id="21156-127">Requirements</span></span>  
 <span data-ttu-id="21156-128">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="21156-128">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="21156-129">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="21156-129">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="21156-130">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="21156-130">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="21156-131">Vea también</span><span class="sxs-lookup"><span data-stu-id="21156-131">See also</span></span>

- [<span data-ttu-id="21156-132">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="21156-132">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
