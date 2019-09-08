---
title: Función SpawnDerivedClass (referencia de la API no administrada)
description: La función SpawnDerivedClass crea un nuevo objeto que se deriva de un objeto.
ms.date: 11/06/2017
api_name:
- SpawnDerivedClass
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- SpawnDerivedClass
helpviewer_keywords:
- SpawnDerivedClass function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c213f311f1af1e56d0ce24eba3b76f33be541323
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798232"
---
# <a name="spawnderivedclass-function"></a><span data-ttu-id="5220f-103">SpawnDerivedClass función)</span><span class="sxs-lookup"><span data-stu-id="5220f-103">SpawnDerivedClass function</span></span>
<span data-ttu-id="5220f-104">Crea un objeto de clase recién derivado a partir de un objeto específico.</span><span class="sxs-lookup"><span data-stu-id="5220f-104">Creates a newly derived class object from a specified object.</span></span>    
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="5220f-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="5220f-105">Syntax</span></span>  
  
```cpp  
HRESULT SpawnDerivedClass (
   [in] int                  vFunc, 
   [in] IWbemClassObject*    ptr, 
   [in] LONG                 lFlags,
   [out] IWbemClassObject**  ppNewClass); 
```  

## <a name="parameters"></a><span data-ttu-id="5220f-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="5220f-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="5220f-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="5220f-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="5220f-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="5220f-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`lFlags`  
<span data-ttu-id="5220f-109">[in] Reservado.</span><span class="sxs-lookup"><span data-stu-id="5220f-109">[in] Reserved.</span></span> <span data-ttu-id="5220f-110">Este parámetro debe ser 0.</span><span class="sxs-lookup"><span data-stu-id="5220f-110">This parameter must be 0.</span></span>

`ppNewClass`  
<span data-ttu-id="5220f-111">enuncia Recibe el puntero al nuevo objeto de definición de clase.</span><span class="sxs-lookup"><span data-stu-id="5220f-111">[out] Receives the pointer to the new class definition object.</span></span> <span data-ttu-id="5220f-112">Si se produce un error, no se devuelve un nuevo objeto y `ppNewClass` se deja sin modificar.</span><span class="sxs-lookup"><span data-stu-id="5220f-112">If an error occurs, a new object is not returned, and `ppNewClass` is left unmodified.</span></span> <span data-ttu-id="5220f-113">Su valor no puede `null`ser.</span><span class="sxs-lookup"><span data-stu-id="5220f-113">Its value cannot be `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="5220f-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="5220f-114">Return value</span></span>

<span data-ttu-id="5220f-115">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="5220f-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="5220f-116">Constante</span><span class="sxs-lookup"><span data-stu-id="5220f-116">Constant</span></span>  |<span data-ttu-id="5220f-117">Valor</span><span class="sxs-lookup"><span data-stu-id="5220f-117">Value</span></span>  |<span data-ttu-id="5220f-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="5220f-118">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="5220f-119">0x80041001</span><span class="sxs-lookup"><span data-stu-id="5220f-119">0x80041001</span></span> | <span data-ttu-id="5220f-120">Se ha producido un error general.</span><span class="sxs-lookup"><span data-stu-id="5220f-120">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="5220f-121">0x80041016</span><span class="sxs-lookup"><span data-stu-id="5220f-121">0x80041016</span></span> | <span data-ttu-id="5220f-122">Se solicitó una operación no válida, como la generación de una clase a partir de una instancia.</span><span class="sxs-lookup"><span data-stu-id="5220f-122">An invalid operation, such as spawning a class from an instance, was requested.</span></span> |
| `WBEM_E_INCOMPLETE_CLASS` | <span data-ttu-id="5220f-123">La clase de origen no se definió por completo ni se registró con la administración de Windows, por lo que no se permite una nueva clase derivada.</span><span class="sxs-lookup"><span data-stu-id="5220f-123">The source class was not completely defined or registered with Windows Management, so a new derived class is not permitted.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="5220f-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="5220f-124">0x80041006</span></span> | <span data-ttu-id="5220f-125">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="5220f-125">Not enough memory is available to complete the operation.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="5220f-126">0x80041008</span><span class="sxs-lookup"><span data-stu-id="5220f-126">0x80041008</span></span> | <span data-ttu-id="5220f-127">El valor de `ppNewClass` es `null`.</span><span class="sxs-lookup"><span data-stu-id="5220f-127">`ppNewClass` is `null`.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="5220f-128">0</span><span class="sxs-lookup"><span data-stu-id="5220f-128">0</span></span> | <span data-ttu-id="5220f-129">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="5220f-129">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="5220f-130">Comentarios</span><span class="sxs-lookup"><span data-stu-id="5220f-130">Remarks</span></span>

<span data-ttu-id="5220f-131">Esta función contiene una llamada al método [IWbemClassObject:: SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) .</span><span class="sxs-lookup"><span data-stu-id="5220f-131">This function wraps a call to the [IWbemClassObject::SpawnDerivedClass](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-clone) method.</span></span>

<span data-ttu-id="5220f-132">`ptr`debe ser una definición de clase que se convierte en la clase primaria del objeto generado.</span><span class="sxs-lookup"><span data-stu-id="5220f-132">`ptr` must be a class definition that becomes the parent class of the spawned object.</span></span> <span data-ttu-id="5220f-133">El objeto devuelto se convierte en una subclase del objeto actual.</span><span class="sxs-lookup"><span data-stu-id="5220f-133">The returned object becomes a subclass of the current object.</span></span>

<span data-ttu-id="5220f-134">El nuevo objeto devuelto `ppNewClass` en se convierte automáticamente en una subclase del objeto actual.</span><span class="sxs-lookup"><span data-stu-id="5220f-134">The new object returned in `ppNewClass` automatically becomes a subclass of the current object.</span></span> <span data-ttu-id="5220f-135">Este comportamiento no se puede invalidar.</span><span class="sxs-lookup"><span data-stu-id="5220f-135">This behavior cannot be overridden.</span></span> <span data-ttu-id="5220f-136">No hay ningún otro método por el que se puedan crear subclases (clases derivadas).</span><span class="sxs-lookup"><span data-stu-id="5220f-136">There is no other method by which subclasses (derived classes) can be created.</span></span>

## <a name="requirements"></a><span data-ttu-id="5220f-137">Requisitos</span><span class="sxs-lookup"><span data-stu-id="5220f-137">Requirements</span></span>  
 <span data-ttu-id="5220f-138">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="5220f-138">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5220f-139">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="5220f-139">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="5220f-140">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="5220f-140">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5220f-141">Vea también</span><span class="sxs-lookup"><span data-stu-id="5220f-141">See also</span></span>

- [<span data-ttu-id="5220f-142">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="5220f-142">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
