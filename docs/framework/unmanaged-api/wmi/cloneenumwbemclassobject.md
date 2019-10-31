---
title: Función CloneEnumWbemClassObject (referencia de la API no administrada)
description: La función CloneEnumWbemClassObject realiza una copia lógica de un enumerador.
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
ms.openlocfilehash: 9d2442161aaa83693a33f9efc230c09b8c4426e2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73128734"
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="450c6-103">Función CloneEnumWbemClassObject</span><span class="sxs-lookup"><span data-stu-id="450c6-103">CloneEnumWbemClassObject function</span></span>
<span data-ttu-id="450c6-104">Realiza una copia lógica de un enumerador conservando su posición actual en una enumeración.</span><span class="sxs-lookup"><span data-stu-id="450c6-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="450c6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="450c6-105">Syntax</span></span>

```cpp
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

## <a name="parameters"></a><span data-ttu-id="450c6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="450c6-106">Parameters</span></span>

`ppEnum`\
<span data-ttu-id="450c6-107">enuncia Recibe un puntero a un nuevo [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="450c6-107">[out] Receives a pointer to a new [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span></span>

`authLevel`\
<span data-ttu-id="450c6-108">de Nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="450c6-108">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="450c6-109">de Nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="450c6-109">[in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`\
<span data-ttu-id="450c6-110">enuncia Puntero a la instancia de [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) que se va a clonar.</span><span class="sxs-lookup"><span data-stu-id="450c6-110">[out] A pointer to the [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) instance to be cloned.</span></span>

`strUser`\
<span data-ttu-id="450c6-111">de El nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="450c6-111">[in] The user name.</span></span> <span data-ttu-id="450c6-112">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="450c6-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="450c6-113">de La contraseña.</span><span class="sxs-lookup"><span data-stu-id="450c6-113">[in] The password.</span></span> <span data-ttu-id="450c6-114">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="450c6-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="450c6-115">`strAuthority`\ [in] el nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="450c6-115">`strAuthority`\ [in] The domain name of the user.</span></span> <span data-ttu-id="450c6-116">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="450c6-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="450c6-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="450c6-117">Return value</span></span>

<span data-ttu-id="450c6-118">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="450c6-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="450c6-119">Constante</span><span class="sxs-lookup"><span data-stu-id="450c6-119">Constant</span></span>  |<span data-ttu-id="450c6-120">Valor</span><span class="sxs-lookup"><span data-stu-id="450c6-120">Value</span></span>  |<span data-ttu-id="450c6-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="450c6-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="450c6-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="450c6-122">0x80041001</span></span> | <span data-ttu-id="450c6-123">Se ha producido un error general.</span><span class="sxs-lookup"><span data-stu-id="450c6-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="450c6-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="450c6-124">0x80041008</span></span> | <span data-ttu-id="450c6-125">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="450c6-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="450c6-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="450c6-126">0x80041006</span></span> | <span data-ttu-id="450c6-127">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="450c6-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="450c6-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="450c6-128">0x80041015</span></span> | <span data-ttu-id="450c6-129">Error en el vínculo de llamada a procedimiento remoto (RPC) entre el proceso actual y WMI.</span><span class="sxs-lookup"><span data-stu-id="450c6-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="450c6-130">0</span><span class="sxs-lookup"><span data-stu-id="450c6-130">0</span></span> | <span data-ttu-id="450c6-131">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="450c6-131">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="450c6-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="450c6-132">Remarks</span></span>

<span data-ttu-id="450c6-133">Esta función contiene una llamada al método [IEnumWbemClassObject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) .</span><span class="sxs-lookup"><span data-stu-id="450c6-133">This function wraps a call to the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

<span data-ttu-id="450c6-134">Este método solo realiza una copia de "mejor esfuerzo".</span><span class="sxs-lookup"><span data-stu-id="450c6-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="450c6-135">Debido a la naturaleza dinámica de muchos objetos CIM, es posible que el nuevo enumerador no enumere el mismo conjunto de objetos que el enumerador de origen.</span><span class="sxs-lookup"><span data-stu-id="450c6-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>

<span data-ttu-id="450c6-136">Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la función [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="450c6-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="450c6-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="450c6-137">Example</span></span>

<span data-ttu-id="450c6-138">Para obtener un ejemplo, vea el método [IEnumWbemClassObject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) .</span><span class="sxs-lookup"><span data-stu-id="450c6-138">For an example, see the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="450c6-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="450c6-139">Requirements</span></span>
 <span data-ttu-id="450c6-140">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="450c6-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="450c6-141">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="450c6-141">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="450c6-142">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="450c6-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="450c6-143">Vea también</span><span class="sxs-lookup"><span data-stu-id="450c6-143">See also</span></span>

- [<span data-ttu-id="450c6-144">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="450c6-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
