---
title: Función SpawnInstance (referencia de la API no administrada)
description: La función SpawnInstance crea una nueva instancia de una clase.
ms.date: 11/06/2017
api_name:
- SpawnInstance
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnInstance
helpviewer_keywords:
- SpawnInstance function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 176bc83dd02381af8c2bc3995a37e7fee7c1bebf
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732234"
---
# <a name="spawninstance-function"></a><span data-ttu-id="e311d-103">Función SpawnInstance</span><span class="sxs-lookup"><span data-stu-id="e311d-103">SpawnInstance function</span></span>

<span data-ttu-id="e311d-104">Crea una instancia a partir de una clase.</span><span class="sxs-lookup"><span data-stu-id="e311d-104">Creates a new instance of a class.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="e311d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e311d-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnInstance (
   [in] int                  vFunc,
   [in] IWbemClassObject*    ptr,
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance);
```  

## <a name="parameters"></a><span data-ttu-id="e311d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e311d-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e311d-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="e311d-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e311d-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="e311d-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="e311d-109">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="e311d-109">[in] Reserved.</span></span> <span data-ttu-id="e311d-110">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="e311d-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="e311d-111">enuncia Recibe el puntero a la nueva instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="e311d-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="e311d-112">Si se produce un error, no se devuelve un nuevo objeto y `ppNewInstance` se deja sin modificar.</span><span class="sxs-lookup"><span data-stu-id="e311d-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="e311d-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e311d-113">Return value</span></span>

<span data-ttu-id="e311d-114">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="e311d-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e311d-115">Constante</span><span class="sxs-lookup"><span data-stu-id="e311d-115">Constant</span></span>  |<span data-ttu-id="e311d-116">Value</span><span class="sxs-lookup"><span data-stu-id="e311d-116">Value</span></span>  |<span data-ttu-id="e311d-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="e311d-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="e311d-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="e311d-118">0x80041020</span></span> | <span data-ttu-id="e311d-119">`ptr` no es una definición de clase válida y no puede generar nuevas instancias.</span><span class="sxs-lookup"><span data-stu-id="e311d-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="e311d-120">O bien está incompleto o no se ha registrado con la administración de Windows mediante una llamada a [PutClassWmi](putclasswmi.md).</span><span class="sxs-lookup"><span data-stu-id="e311d-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="e311d-121">0x80041006</span><span class="sxs-lookup"><span data-stu-id="e311d-121">0x80041006</span></span> | <span data-ttu-id="e311d-122">Memoria insuficiente para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="e311d-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e311d-123">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e311d-123">0x80041008</span></span> | <span data-ttu-id="e311d-124">`ppNewClass` es `null`.</span><span class="sxs-lookup"><span data-stu-id="e311d-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="e311d-125">0</span><span class="sxs-lookup"><span data-stu-id="e311d-125">0</span></span> | <span data-ttu-id="e311d-126">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e311d-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e311d-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e311d-127">Remarks</span></span>

<span data-ttu-id="e311d-128">Esta función contiene una llamada al método [IWbemClassObject:: SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) .</span><span class="sxs-lookup"><span data-stu-id="e311d-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-spawninstance) method.</span></span>

<span data-ttu-id="e311d-129">`ptr` debe ser una definición de clase obtenida de la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="e311d-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="e311d-130">(Tenga en cuenta que se admite la generación de una instancia a partir de una instancia de, pero la instancia devuelta está vacía). A continuación, use esta definición de clase para crear nuevas instancias.</span><span class="sxs-lookup"><span data-stu-id="e311d-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="e311d-131">Se requiere una llamada a la función [PutInstanceWmi](putinstancewmi.md) si desea escribir la instancia en la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="e311d-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>

<span data-ttu-id="e311d-132">El nuevo objeto devuelto en `ppNewClass` se convierte automáticamente en una subclase del objeto actual.</span><span class="sxs-lookup"><span data-stu-id="e311d-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="e311d-133">Este comportamiento no se puede invalidar.</span><span class="sxs-lookup"><span data-stu-id="e311d-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="e311d-134">No hay ningún otro método por el que se puedan crear subclases (clases derivadas).</span><span class="sxs-lookup"><span data-stu-id="e311d-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="e311d-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e311d-135">Requirements</span></span>  

 <span data-ttu-id="e311d-136">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e311d-136">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e311d-137">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="e311d-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e311d-138">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e311d-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e311d-139">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e311d-139">See also</span></span>

- [<span data-ttu-id="e311d-140">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="e311d-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
