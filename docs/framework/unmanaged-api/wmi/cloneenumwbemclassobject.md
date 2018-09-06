---
title: CloneEnumWbemClassObject (función) (referencia de API no administrada)
description: CloneEnumWbemClassObject (función) realiza una copia lógica de un enumerador.
ms.date: 11/06/2017
api_name:
- CloneEnumWbemClassObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- CloneEnumWbemClassObject
helpviewer_keywords:
- CloneEnumWbemClassObject function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 35bd458eb6046f57d37764e0a8e58616f2c2c3a1
ms.sourcegitcommit: 3c1c3ba79895335ff3737934e39372555ca7d6d0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/05/2018
ms.locfileid: "43778537"
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="31020-103">CloneEnumWbemClassObject (función)</span><span class="sxs-lookup"><span data-stu-id="31020-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="31020-104">Realiza una copia lógica de un enumerador conservando su posición actual en una enumeración.</span><span class="sxs-lookup"><span data-stu-id="31020-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>  
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="31020-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="31020-105">Syntax</span></span>  
  
```  
HRESULT CloneEnumWbemClassObject (
   [out] IEnumWbemClassObject**  ppEnum, 
   [in] DWORD                    authLevel,
   [in] DWORD                    impLevel,
   [in] IEnumWbemClassObject*    pCurrentEnumWbemClassObject, 
   [in] BSTR                     strUser,
   [in] BSTR                     strPassword,
   [in BSTR]                     strAuthority 
); 
```  

## <a name="parameters"></a><span data-ttu-id="31020-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="31020-106">Parameters</span></span>

`ppEnum`  
<span data-ttu-id="31020-107">[out] Recibe un puntero a un nuevo [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="31020-107">[out] Receives a pointer to a new [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span></span>

`authLevel`  
<span data-ttu-id="31020-108">[in] El nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="31020-108">[in] The authorization level.</span></span>

<span data-ttu-id="31020-109">`impLevel` [in] El nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="31020-109">`impLevel` [in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`  
<span data-ttu-id="31020-110">[out] Un puntero a la [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) instancia para clonarse.</span><span class="sxs-lookup"><span data-stu-id="31020-110">[out] A pointer to the [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) instance to be cloned.</span></span>

`strUser`   
<span data-ttu-id="31020-111">[in] El nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="31020-111">[in] The user name.</span></span> <span data-ttu-id="31020-112">Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="31020-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`   
<span data-ttu-id="31020-113">[in] La contraseña.</span><span class="sxs-lookup"><span data-stu-id="31020-113">[in] The password.</span></span> <span data-ttu-id="31020-114">Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="31020-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`   
<span data-ttu-id="31020-115">[in] El nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="31020-115">[in] The domain name of the user.</span></span> <span data-ttu-id="31020-116">Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="31020-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="31020-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="31020-117">Return value</span></span>

<span data-ttu-id="31020-118">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="31020-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="31020-119">Constante</span><span class="sxs-lookup"><span data-stu-id="31020-119">Constant</span></span>  |<span data-ttu-id="31020-120">Valor</span><span class="sxs-lookup"><span data-stu-id="31020-120">Value</span></span>  |<span data-ttu-id="31020-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="31020-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="31020-122">0 x 80041001</span><span class="sxs-lookup"><span data-stu-id="31020-122">0x80041001</span></span> | <span data-ttu-id="31020-123">Ha habido un error general.</span><span class="sxs-lookup"><span data-stu-id="31020-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="31020-124">0 x 80041008</span><span class="sxs-lookup"><span data-stu-id="31020-124">0x80041008</span></span> | <span data-ttu-id="31020-125">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="31020-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="31020-126">0 x 80041006</span><span class="sxs-lookup"><span data-stu-id="31020-126">0x80041006</span></span> | <span data-ttu-id="31020-127">No hay suficiente memoria disponible completar la operación.</span><span class="sxs-lookup"><span data-stu-id="31020-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="31020-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="31020-128">0x80041015</span></span> | <span data-ttu-id="31020-129">Error en el vínculo de procedimiento remoto (RPC) de la llamada entre el proceso actual y WMI.</span><span class="sxs-lookup"><span data-stu-id="31020-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="31020-130">0</span><span class="sxs-lookup"><span data-stu-id="31020-130">0</span></span> | <span data-ttu-id="31020-131">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="31020-131">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="31020-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="31020-132">Remarks</span></span>

<span data-ttu-id="31020-133">Esta función contiene una llamada a la [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) método.</span><span class="sxs-lookup"><span data-stu-id="31020-133">This function wraps a call to the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

<span data-ttu-id="31020-134">Este método realiza solo una copia de "mejor esfuerzo".</span><span class="sxs-lookup"><span data-stu-id="31020-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="31020-135">Dada la naturaleza dinámica de muchos objetos CIM, es posible que el nuevo enumerador no enumere el mismo conjunto de objetos que el enumerador de código fuente.</span><span class="sxs-lookup"><span data-stu-id="31020-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>  

<span data-ttu-id="31020-136">Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la [GetErrorInfo](geterrorinfo.md) función.</span><span class="sxs-lookup"><span data-stu-id="31020-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="31020-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="31020-137">Example</span></span>

<span data-ttu-id="31020-138">Para obtener un ejemplo, vea el [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) método.</span><span class="sxs-lookup"><span data-stu-id="31020-138">For an example, see the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="31020-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="31020-139">Requirements</span></span>  
 <span data-ttu-id="31020-140">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="31020-140">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="31020-141">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="31020-141">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="31020-142">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="31020-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="31020-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="31020-143">See also</span></span>  
[<span data-ttu-id="31020-144">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="31020-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
