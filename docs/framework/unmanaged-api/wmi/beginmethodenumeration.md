---
title: "Función BeginMethodEnumeration (referencia de API no administrada)"
description: "La función BeginMethodEnumeration comienza una enumeración de los métodos del objeto"
ms.date: 11/06/2017
ms.prod: .net-framework
ms.technology: dotnet-clr
ms.topic: reference
api_name: BeginMethodEnumeration
api_location: WMINet_Utils.dll
api_type: DLLExport
f1_keywords: BeginMethodEnumeration
helpviewer_keywords: BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type: Reference
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2e44c432f9503f96ad4dab9e25b78e6dd148f94c
ms.sourcegitcommit: a53799f81351ad9afb3007cd68846ce6aeeb10cb
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/15/2017
---
# <a name="beginenumeration-function"></a><span data-ttu-id="becae-103">BeginEnumeration (función)</span><span class="sxs-lookup"><span data-stu-id="becae-103">BeginEnumeration function</span></span>
<span data-ttu-id="becae-104">Comienza una enumeración de los métodos disponibles para el objeto.</span><span class="sxs-lookup"><span data-stu-id="becae-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="becae-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="becae-105">Syntax</span></span>  
  
``` 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="becae-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="becae-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="becae-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="becae-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="becae-108">[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="becae-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="becae-109">[in] Cero (0) para todos los métodos, o una marca que especifica el ámbito de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="becae-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="becae-110">Las marcas siguientes se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="becae-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="becae-111">Constante</span><span class="sxs-lookup"><span data-stu-id="becae-111">Constant</span></span>  |<span data-ttu-id="becae-112">Valor</span><span class="sxs-lookup"><span data-stu-id="becae-112">Value</span></span>  |<span data-ttu-id="becae-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="becae-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="becae-114">0 x 10</span><span class="sxs-lookup"><span data-stu-id="becae-114">0x10</span></span> | <span data-ttu-id="becae-115">Limitar la enumeración a los métodos que se definen en la propia clase.</span><span class="sxs-lookup"><span data-stu-id="becae-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="becae-116">0 x 20</span><span class="sxs-lookup"><span data-stu-id="becae-116">0x20</span></span> | <span data-ttu-id="becae-117">Limitar la enumeración de propiedades que se heredan de clases base.</span><span class="sxs-lookup"><span data-stu-id="becae-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="becae-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="becae-118">Return value</span></span>

<span data-ttu-id="becae-119">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="becae-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="becae-120">Constante</span><span class="sxs-lookup"><span data-stu-id="becae-120">Constant</span></span>  |<span data-ttu-id="becae-121">Valor</span><span class="sxs-lookup"><span data-stu-id="becae-121">Value</span></span>  |<span data-ttu-id="becae-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="becae-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="becae-123">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="becae-123">0x80041008</span></span> | <span data-ttu-id="becae-124">`lEnnumFlags`es distinto de cero y no es uno de los indicadores especificados.</span><span class="sxs-lookup"><span data-stu-id="becae-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="becae-125">0</span><span class="sxs-lookup"><span data-stu-id="becae-125">0</span></span> | <span data-ttu-id="becae-126">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="becae-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="becae-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="becae-127">Remarks</span></span>

<span data-ttu-id="becae-128">Esta función contiene una llamada a la [IWbemClassObject::BeginMethodEnumeration](https://msdn.microsoft.com/library/aa391435(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="becae-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](https://msdn.microsoft.com/library/aa391435(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="becae-129">Llamar a este método solo se admite si el objeto actual es una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="becae-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="becae-130">Manipulación de método no está disponible en [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) punteros que señalan a las instancias.</span><span class="sxs-lookup"><span data-stu-id="becae-130">Method manipulation is not available from [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) pointers that point to instances.</span></span> <span data-ttu-id="becae-131">Se garantiza el orden en el que se enumeran los métodos que sea invariable para una instancia determinada de [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx).</span><span class="sxs-lookup"><span data-stu-id="becae-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx).</span></span>

## <a name="requirements"></a><span data-ttu-id="becae-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="becae-132">Requirements</span></span>  
 <span data-ttu-id="becae-133">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="becae-133">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="becae-134">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="becae-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="becae-135">**Versiones de .NET framework:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="becae-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="becae-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="becae-136">See also</span></span>  
[<span data-ttu-id="becae-137">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="becae-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
