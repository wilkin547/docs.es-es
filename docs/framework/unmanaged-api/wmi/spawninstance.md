---
title: Función SpawnInstance (referencia de API no administrada)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 3f8189f0adb62aa32cd0b85ca5a653aa466c7032
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33460468"
---
# <a name="spawninstance-function"></a><span data-ttu-id="3175c-103">Función SpawnInstance</span><span class="sxs-lookup"><span data-stu-id="3175c-103">SpawnInstance function</span></span>
<span data-ttu-id="3175c-104">Crea una nueva instancia de una clase.</span><span class="sxs-lookup"><span data-stu-id="3175c-104">Creates a new instance of a class.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="3175c-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3175c-105">Syntax</span></span>  
  
```  
HRESULT SpawnInstance (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewInstance); 
```  

## <a name="parameters"></a><span data-ttu-id="3175c-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3175c-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3175c-107">[in] Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="3175c-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="3175c-108">[in] Un puntero a un [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instancia.</span><span class="sxs-lookup"><span data-stu-id="3175c-108">[in] A pointer to an [IWbemClassObject](https://msdn.microsoft.com/library/aa391433%28v=vs.85%29.aspx) instance.</span></span>

`lFlags`  
<span data-ttu-id="3175c-109">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="3175c-109">[in] Reserved.</span></span> <span data-ttu-id="3175c-110">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="3175c-110">This parameter must be 0.</span></span>

`ppNewInstance`  
<span data-ttu-id="3175c-111">[out] Recibe el puntero a la nueva instancia de la clase.</span><span class="sxs-lookup"><span data-stu-id="3175c-111">[out] Receives the pointer to the new instance of the class.</span></span> <span data-ttu-id="3175c-112">Si se produce un error, no es un nuevo objeto devuelto, y `ppNewInstance` es izquierda sin modificar.</span><span class="sxs-lookup"><span data-stu-id="3175c-112">If an error occurs, a new object is not returned, and `ppNewInstance` is left unmodified.</span></span>

## <a name="return-value"></a><span data-ttu-id="3175c-113">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3175c-113">Return value</span></span>

<span data-ttu-id="3175c-114">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, o bien puede definirlas como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="3175c-114">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3175c-115">Constante</span><span class="sxs-lookup"><span data-stu-id="3175c-115">Constant</span></span>  |<span data-ttu-id="3175c-116">Valor</span><span class="sxs-lookup"><span data-stu-id="3175c-116">Value</span></span>  |<span data-ttu-id="3175c-117">Descripción</span><span class="sxs-lookup"><span data-stu-id="3175c-117">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="3175c-118">0x80041020</span><span class="sxs-lookup"><span data-stu-id="3175c-118">0x80041020</span></span> | <span data-ttu-id="3175c-119">`ptr` no es una definición de clase válido y no se puede generar nuevas instancias.</span><span class="sxs-lookup"><span data-stu-id="3175c-119">`ptr` is not a valid class definition and cannot spawn new instances.</span></span> <span data-ttu-id="3175c-120">Está incompleto o no se ha registrado con la administración de Windows mediante una llamada a [PutClassWmi](putclasswmi.md).</span><span class="sxs-lookup"><span data-stu-id="3175c-120">Either it is incomplete or it has not been registered with Windows Management by calling [PutClassWmi](putclasswmi.md).</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="3175c-121">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="3175c-121">0x80041006</span></span> | <span data-ttu-id="3175c-122">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="3175c-122">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3175c-123">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="3175c-123">0x80041008</span></span> | <span data-ttu-id="3175c-124">El valor de `ppNewClass` es `null`.</span><span class="sxs-lookup"><span data-stu-id="3175c-124">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="3175c-125">0</span><span class="sxs-lookup"><span data-stu-id="3175c-125">0</span></span> | <span data-ttu-id="3175c-126">La llamada de función tuvo éxito.</span><span class="sxs-lookup"><span data-stu-id="3175c-126">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="3175c-127">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3175c-127">Remarks</span></span>

<span data-ttu-id="3175c-128">Esta función contiene una llamada a la [IWbemClassObject:: SpawnInstance](https://msdn.microsoft.com/library/aa391458(v=vs.85).aspx) método.</span><span class="sxs-lookup"><span data-stu-id="3175c-128">This function wraps a call to the [IWbemClassObject::SpawnInstance](https://msdn.microsoft.com/library/aa391458(v=vs.85).aspx) method.</span></span>

<span data-ttu-id="3175c-129">`ptr` debe ser una definición de clase obtenida de la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="3175c-129">`ptr` must be a class definition obtained from Windows Management.</span></span> <span data-ttu-id="3175c-130">(Tenga en cuenta que se admite la creación de una instancia de una instancia, pero la instancia devuelta está vacía). A continuación, utilizar esta definición de clase para crear nuevas instancias.</span><span class="sxs-lookup"><span data-stu-id="3175c-130">(Note that spawning an instance from an instance is supported but the returned instance is empty.) You then use this class definition to create new instances.</span></span> <span data-ttu-id="3175c-131">Una llamada a la [PutInstanceWmi](putinstancewmi.md) función es necesaria si se va a escribir la instancia a la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="3175c-131">A call to the [PutInstanceWmi](putinstancewmi.md) function is required if you intend to write the instance to Windows Management.</span></span>




<span data-ttu-id="3175c-132">El nuevo objeto devuelto en `ppNewClass` se convierte automáticamente en una subclase del objeto actual.</span><span class="sxs-lookup"><span data-stu-id="3175c-132">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="3175c-133">No se puede invalidar este comportamiento.</span><span class="sxs-lookup"><span data-stu-id="3175c-133">This behavior cannot be overridden.</span></span> <span data-ttu-id="3175c-134">No hay ningún otro método por el que se pueden crear subclases (clases derivadas).</span><span class="sxs-lookup"><span data-stu-id="3175c-134">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="3175c-135">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3175c-135">Requirements</span></span>  
 <span data-ttu-id="3175c-136">**Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3175c-136">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3175c-137">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3175c-137">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3175c-138">**Versiones de .NET framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3175c-138">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3175c-139">Vea también</span><span class="sxs-lookup"><span data-stu-id="3175c-139">See also</span></span>  
[<span data-ttu-id="3175c-140">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="3175c-140">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
