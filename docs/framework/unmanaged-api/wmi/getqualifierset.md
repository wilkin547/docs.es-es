---
title: Función GetQualifierSet (Referencia de API no administrada)
description: La función GetQualifierSet recupera el calificador establecido para una clase o instancia.
ms.date: 11/06/2017
api_name:
- GetQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetQualifierSet
helpviewer_keywords:
- GetQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 368f0a13871bd48780fa30b370d37157d2724bb8
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176778"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="ff096-103">Función GetQualifierSet</span><span class="sxs-lookup"><span data-stu-id="ff096-103">GetQualifierSet function</span></span>
<span data-ttu-id="ff096-104">Recupera el calificador establecido para una instancia o una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="ff096-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="ff096-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ff096-105">Syntax</span></span>  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [out] IWbemQualifierSet  **ppQualSet
);
```  

## <a name="parameters"></a><span data-ttu-id="ff096-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ff096-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="ff096-107">[en] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="ff096-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="ff096-108">[en] Puntero a una instancia de [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="ff096-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="ff096-109">[fuera] Recibe el puntero de interfaz que permite el acceso a los calificadores del objeto de clase.</span><span class="sxs-lookup"><span data-stu-id="ff096-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="ff096-110">El valor de `ppQualSet` no puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="ff096-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="ff096-111">Si se produce un error, no se devuelve un nuevo objeto y el puntero se deja sin modificar.</span><span class="sxs-lookup"><span data-stu-id="ff096-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="ff096-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ff096-112">Return value</span></span>

<span data-ttu-id="ff096-113">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="ff096-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ff096-114">Constante</span><span class="sxs-lookup"><span data-stu-id="ff096-114">Constant</span></span>  |<span data-ttu-id="ff096-115">Value</span><span class="sxs-lookup"><span data-stu-id="ff096-115">Value</span></span>  |<span data-ttu-id="ff096-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="ff096-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="ff096-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="ff096-117">0x80041001</span></span> | <span data-ttu-id="ff096-118">Ha habido un fracaso general.</span><span class="sxs-lookup"><span data-stu-id="ff096-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="ff096-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="ff096-119">0x80041002</span></span> | <span data-ttu-id="ff096-120">El método especificado no existe.</span><span class="sxs-lookup"><span data-stu-id="ff096-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="ff096-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="ff096-121">0x80041006</span></span> | <span data-ttu-id="ff096-122">Memoria insuficiente para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="ff096-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="ff096-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="ff096-123">0x80041008</span></span> | <span data-ttu-id="ff096-124">Un parámetro `null`es .</span><span class="sxs-lookup"><span data-stu-id="ff096-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="ff096-125">0</span><span class="sxs-lookup"><span data-stu-id="ff096-125">0</span></span> | <span data-ttu-id="ff096-126">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ff096-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="ff096-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="ff096-127">Remarks</span></span>

<span data-ttu-id="ff096-128">Esta función ajusta una llamada a la [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) método.</span><span class="sxs-lookup"><span data-stu-id="ff096-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span>

<span data-ttu-id="ff096-129">El [puntero IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) permite al autor de la llamada agregar, editar o eliminar estos calificadores.</span><span class="sxs-lookup"><span data-stu-id="ff096-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="ff096-130">Estos calificadores agregados, editados o eliminados se aplican a toda la definición de instancia o clase.</span><span class="sxs-lookup"><span data-stu-id="ff096-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="ff096-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ff096-131">Requirements</span></span>  
<span data-ttu-id="ff096-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ff096-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ff096-133">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ff096-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ff096-134">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ff096-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ff096-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ff096-135">See also</span></span>

- [<span data-ttu-id="ff096-136">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="ff096-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
