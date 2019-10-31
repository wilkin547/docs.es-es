---
title: Función BeginMethodEnumeration (referencia de la API no administrada)
description: La función BeginMethodEnumeration inicia una enumeración de los métodos del objeto.
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
ms.openlocfilehash: a27787052757098d4edb2d8516e22d8a03b7009a
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73138785"
---
# <a name="beginenumeration-function"></a><span data-ttu-id="2396c-103">Función BeginEnumeration</span><span class="sxs-lookup"><span data-stu-id="2396c-103">BeginEnumeration function</span></span>
<span data-ttu-id="2396c-104">Comienza una enumeración de los métodos disponibles para el objeto.</span><span class="sxs-lookup"><span data-stu-id="2396c-104">Begins an enumeration of the methods available for the object.</span></span>  

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="2396c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="2396c-105">Syntax</span></span>  
  
```cpp 
HRESULT BeginMethodEnumeration (
   [in] int               vFunc, 
   [in] IWbemClassObject* ptr, 
   [in] LONG              lEnumFlags
); 
```  

## <a name="parameters"></a><span data-ttu-id="2396c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="2396c-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="2396c-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="2396c-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="2396c-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="2396c-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lEnumFlags`  
<span data-ttu-id="2396c-109">de Cero (0) para todos los métodos, o una marca que especifica el ámbito de la enumeración.</span><span class="sxs-lookup"><span data-stu-id="2396c-109">[in] Zero (0) for all methods, or a flag that specifies the scope of the enumeration.</span></span> <span data-ttu-id="2396c-110">Las marcas siguientes se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="2396c-110">The following flags are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

<span data-ttu-id="2396c-111">Constante</span><span class="sxs-lookup"><span data-stu-id="2396c-111">Constant</span></span>  |<span data-ttu-id="2396c-112">Valor</span><span class="sxs-lookup"><span data-stu-id="2396c-112">Value</span></span>  |<span data-ttu-id="2396c-113">Descripción</span><span class="sxs-lookup"><span data-stu-id="2396c-113">Description</span></span>  |
|---------|---------|---------|
| `WBEM_FLAG_LOCAL_ONLY` | <span data-ttu-id="2396c-114">0x10</span><span class="sxs-lookup"><span data-stu-id="2396c-114">0x10</span></span> | <span data-ttu-id="2396c-115">Limite la enumeración a los métodos que se definen en la propia clase.</span><span class="sxs-lookup"><span data-stu-id="2396c-115">Limit the enumeration to methods that are defined in the class itself.</span></span> |
| `WBEM_FLAG_PROPAGATED_ONLY` |  <span data-ttu-id="2396c-116">0x20</span><span class="sxs-lookup"><span data-stu-id="2396c-116">0x20</span></span> | <span data-ttu-id="2396c-117">Limite la enumeración a las propiedades que se heredan de las clases base.</span><span class="sxs-lookup"><span data-stu-id="2396c-117">Limit the enumeration to properties that are inherited from base classes.</span></span> |

## <a name="return-value"></a><span data-ttu-id="2396c-118">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="2396c-118">Return value</span></span>

<span data-ttu-id="2396c-119">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="2396c-119">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="2396c-120">Constante</span><span class="sxs-lookup"><span data-stu-id="2396c-120">Constant</span></span>  |<span data-ttu-id="2396c-121">Valor</span><span class="sxs-lookup"><span data-stu-id="2396c-121">Value</span></span>  |<span data-ttu-id="2396c-122">Descripción</span><span class="sxs-lookup"><span data-stu-id="2396c-122">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="2396c-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="2396c-123">0x80041008</span></span> | <span data-ttu-id="2396c-124">`lEnnumFlags` es distinto de cero y no es una de las marcas especificadas.</span><span class="sxs-lookup"><span data-stu-id="2396c-124">`lEnnumFlags` is non-zero and is not one of the specified flags.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="2396c-125">0</span><span class="sxs-lookup"><span data-stu-id="2396c-125">0</span></span> | <span data-ttu-id="2396c-126">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="2396c-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="2396c-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="2396c-127">Remarks</span></span>

<span data-ttu-id="2396c-128">Esta función contiene una llamada al método [IWbemClassObject:: BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) .</span><span class="sxs-lookup"><span data-stu-id="2396c-128">This function wraps a call to the [IWbemClassObject::BeginMethodEnumeration](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-beginmethodenumeration) method.</span></span>

<span data-ttu-id="2396c-129">Esta llamada al método solo se admite si el objeto actual es una definición de clase.</span><span class="sxs-lookup"><span data-stu-id="2396c-129">This method call is only supported if the current object is a class definition.</span></span> <span data-ttu-id="2396c-130">La manipulación de métodos no está disponible en punteros [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que apunten a instancias.</span><span class="sxs-lookup"><span data-stu-id="2396c-130">Method manipulation is not available from [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to instances.</span></span> <span data-ttu-id="2396c-131">Se garantiza que el orden en que se enumeran los métodos es invariable para una instancia determinada de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="2396c-131">The order in which methods are enumerated is guaranteed to be invariant for a given instance of [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject).</span></span>

## <a name="requirements"></a><span data-ttu-id="2396c-132">Requisitos</span><span class="sxs-lookup"><span data-stu-id="2396c-132">Requirements</span></span>  
 <span data-ttu-id="2396c-133">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="2396c-133">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2396c-134">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="2396c-134">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="2396c-135">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="2396c-135">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2396c-136">Vea también</span><span class="sxs-lookup"><span data-stu-id="2396c-136">See also</span></span>

- [<span data-ttu-id="2396c-137">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="2396c-137">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
