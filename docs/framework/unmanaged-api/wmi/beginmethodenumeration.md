---
title: Función BeginMethodEnumeration (Referencia de API no administrada)
description: La función BeginMethodEnumeration comienza una enumeración de los métodos del objeto
ms.date: 11/06/2017
api_name:
- BeginMethodEnumeration
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BeginMethodEnumeration
helpviewer_keywords:
- BeginMethodEnumeration function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 876f5810fffab7fa98cd4d46715e13569ab95f6c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79175049"
---
# <a name="beginmethodenumeration-function"></a><span data-ttu-id="eb488-103">Función BeginMethodEnumeration</span><span class="sxs-lookup"><span data-stu-id="eb488-103">BeginMethodEnumeration function</span></span>
<span data-ttu-id="eb488-104">Comienza una enumeración de los métodos disponibles para el objeto.</span><span class="sxs-lookup"><span data-stu-id="eb488-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="eb488-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="eb488-105">Syntax</span></span>  
  
```cpp
HRESULT BeginMethodEnumeration (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LONG              lEnumFlags
);
```  

## <a name="parameters"></a><span data-ttu-id="eb488-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="eb488-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="eb488-107">[en] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="eb488-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="eb488-108">[en] Puntero a una instancia de [IWbemClassObject.](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject)</span><span class="sxs-lookup"><span data-stu-id="eb488-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="eb488-109">[en] Cero (0) para todos los métodos o una marca que especifica el ámbito de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="eb488-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="eb488-110">Los siguientes indicadores se definen en el archivo de encabezado *WbemCli.h* o puede definirlos como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="eb488-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="eb488-111">Constante</span><span class="sxs-lookup"><span data-stu-id="eb488-111">Constant</span></span>  |<span data-ttu-id="eb488-112">Value</span><span class="sxs-lookup"><span data-stu-id="eb488-112">Value</span></span>  |<span data-ttu-id="eb488-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb488-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="eb488-114">0x10</span><span class="sxs-lookup"><span data-stu-id="eb488-114">0x10</span></span> | <span data-ttu-id="eb488-115">Limite la enumeración a los métodos que se definen en la propia clase.</span><span class="sxs-lookup"><span data-stu-id="eb488-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="eb488-116">0x20</span><span class="sxs-lookup"><span data-stu-id="eb488-116">0x20</span></span> | <span data-ttu-id="eb488-117">Limite la enumeración a las propiedades que se heredan de las clases base.</span><span class="sxs-lookup"><span data-stu-id="eb488-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="eb488-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="eb488-118">Return value</span></span>

<span data-ttu-id="eb488-119">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli.h,* o puede definirlos como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="eb488-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="eb488-120">Constante</span><span class="sxs-lookup"><span data-stu-id="eb488-120">Constant</span></span>  |<span data-ttu-id="eb488-121">Value</span><span class="sxs-lookup"><span data-stu-id="eb488-121">Value</span></span>  |<span data-ttu-id="eb488-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="eb488-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="eb488-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="eb488-123">0x80041008</span></span> | <span data-ttu-id="eb488-124">`lEnnumFlags`es distinto de cero y no es uno de los indicadores especificados.</span><span class="sxs-lookup"><span data-stu-id="eb488-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="eb488-125">0</span><span class="sxs-lookup"><span data-stu-id="eb488-125">0</span></span> | <span data-ttu-id="eb488-126">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="eb488-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="eb488-127">Observaciones</span><span class="sxs-lookup"><span data-stu-id="eb488-127">Remarks</span></span>

<span data-ttu-id="eb488-128">Esta función ajusta una llamada a la [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) método.</span><span class="sxs-lookup"><span data-stu-id="eb488-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) method.</span></span>

<span data-ttu-id="eb488-129">Esta llamada al método solo se admite si el objeto actual es una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="eb488-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="eb488-130">La manipulación de métodos no está disponible en los punteros [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que apuntan a instancias.</span><span class="sxs-lookup"><span data-stu-id="eb488-130">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to instances.</span></span> <span data-ttu-id="eb488-131">Se garantiza que el orden en que se enumeran los métodos es invariable para una instancia determinada de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="eb488-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span></span>

## <a name="requirements"></a><span data-ttu-id="eb488-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="eb488-132">Requirements</span></span>  
 <span data-ttu-id="eb488-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="eb488-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="eb488-134">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="eb488-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="eb488-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="eb488-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb488-136">Consulte también</span><span class="sxs-lookup"><span data-stu-id="eb488-136">See also</span></span>

- [<span data-ttu-id="eb488-137">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="eb488-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
