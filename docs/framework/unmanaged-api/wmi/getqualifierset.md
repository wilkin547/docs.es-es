---
title: Función GetQualifierSet (referencia de la API no administrada)
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
ms.openlocfilehash: f9bb882a0f62499167b79bf3e6691d05e394720f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95671348"
---
# <a name="getqualifierset-function"></a><span data-ttu-id="1dae3-103">Función GetQualifierSet</span><span class="sxs-lookup"><span data-stu-id="1dae3-103">GetQualifierSet function</span></span>

<span data-ttu-id="1dae3-104">Recupera el calificador establecido para una instancia o una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="1dae3-104">Retrieves the qualifier set for a class instance or a class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="1dae3-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="1dae3-105">Syntax</span></span>  
  
```cpp  
HRESULT GetQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [out] IWbemQualifierSet  **ppQualSet
);
```  

## <a name="parameters"></a><span data-ttu-id="1dae3-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="1dae3-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="1dae3-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="1dae3-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="1dae3-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="1dae3-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`ppQualSet`  
<span data-ttu-id="1dae3-109">enuncia Recibe el puntero de interfaz que permite el acceso a los calificadores del objeto de clase.</span><span class="sxs-lookup"><span data-stu-id="1dae3-109">[out] Receives the interface pointer that allows access to the qualifiers of the class object.</span></span> <span data-ttu-id="1dae3-110">El valor de `ppQualSet` no puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="1dae3-110">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="1dae3-111">Si se produce un error, no se devuelve un nuevo objeto y el puntero se deja sin modificar.</span><span class="sxs-lookup"><span data-stu-id="1dae3-111">If an error occurs, a new object is not returned, and the pointer is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="1dae3-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="1dae3-112">Return value</span></span>

<span data-ttu-id="1dae3-113">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="1dae3-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="1dae3-114">Constante</span><span class="sxs-lookup"><span data-stu-id="1dae3-114">Constant</span></span>  |<span data-ttu-id="1dae3-115">Value</span><span class="sxs-lookup"><span data-stu-id="1dae3-115">Value</span></span>  |<span data-ttu-id="1dae3-116">Descripción</span><span class="sxs-lookup"><span data-stu-id="1dae3-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_FAILED` | <span data-ttu-id="1dae3-117">0x80041001</span><span class="sxs-lookup"><span data-stu-id="1dae3-117">0x80041001</span></span> | <span data-ttu-id="1dae3-118">Se ha producido un error general.</span><span class="sxs-lookup"><span data-stu-id="1dae3-118">There has been a general failure.</span></span> |
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="1dae3-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="1dae3-119">0x80041002</span></span> | <span data-ttu-id="1dae3-120">El método especificado no existe.</span><span class="sxs-lookup"><span data-stu-id="1dae3-120">The specified method does not exist.</span></span> |
|`WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="1dae3-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="1dae3-121">0x80041006</span></span> | <span data-ttu-id="1dae3-122">Memoria insuficiente para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="1dae3-122">Not enough memory is available to complete the operation.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="1dae3-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="1dae3-123">0x80041008</span></span> | <span data-ttu-id="1dae3-124">Un parámetro es `null` .</span><span class="sxs-lookup"><span data-stu-id="1dae3-124">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="1dae3-125">0</span><span class="sxs-lookup"><span data-stu-id="1dae3-125">0</span></span> | <span data-ttu-id="1dae3-126">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="1dae3-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="1dae3-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="1dae3-127">Remarks</span></span>

<span data-ttu-id="1dae3-128">Esta función contiene una llamada al método [IWbemClassObject:: GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="1dae3-128">This function wraps a call to the [IWbemClassObject::GetQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getqualifierset) method.</span></span>

<span data-ttu-id="1dae3-129">El [puntero IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) permite al autor de la llamada agregar, editar o eliminar estos calificadores.</span><span class="sxs-lookup"><span data-stu-id="1dae3-129">The [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span> <span data-ttu-id="1dae3-130">Tales calificadores agregados, editados o eliminados se aplican a la definición de clase o instancia completa.</span><span class="sxs-lookup"><span data-stu-id="1dae3-130">Such added, edited, or deleted qualifiers apply to the entire instance or class definition.</span></span>

## <a name="requirements"></a><span data-ttu-id="1dae3-131">Requisitos</span><span class="sxs-lookup"><span data-stu-id="1dae3-131">Requirements</span></span>  

<span data-ttu-id="1dae3-132">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="1dae3-132">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1dae3-133">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="1dae3-133">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="1dae3-134">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="1dae3-134">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1dae3-135">Consulte también</span><span class="sxs-lookup"><span data-stu-id="1dae3-135">See also</span></span>

- [<span data-ttu-id="1dae3-136">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="1dae3-136">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
