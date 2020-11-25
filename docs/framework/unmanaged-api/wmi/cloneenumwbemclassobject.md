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
ms.openlocfilehash: fa8a7f436c018e3e083be452d300eb21e17f93f3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708132"
---
# <a name="cloneenumwbemclassobject-function"></a><span data-ttu-id="310ee-103">Función CloneEnumWbemClassObject</span><span class="sxs-lookup"><span data-stu-id="310ee-103">CloneEnumWbemClassObject function</span></span>

<span data-ttu-id="310ee-104">Realiza una copia lógica de un enumerador conservando su posición actual en una enumeración.</span><span class="sxs-lookup"><span data-stu-id="310ee-104">Makes a logical copy of an enumerator, retaining its current position in an enumeration.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="310ee-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="310ee-105">Syntax</span></span>

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

## <a name="parameters"></a><span data-ttu-id="310ee-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="310ee-106">Parameters</span></span>

`ppEnum`\
<span data-ttu-id="310ee-107">enuncia Recibe un puntero a un nuevo [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span><span class="sxs-lookup"><span data-stu-id="310ee-107">[out] Receives a pointer to a new [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject).</span></span>

`authLevel`\
<span data-ttu-id="310ee-108">de Nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="310ee-108">[in] The authorization level.</span></span>

`impLevel`\
<span data-ttu-id="310ee-109">de Nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="310ee-109">[in] The impersonation level.</span></span>

`pCurrentEnumWbemClassObject`\
<span data-ttu-id="310ee-110">enuncia Puntero a la instancia de [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) que se va a clonar.</span><span class="sxs-lookup"><span data-stu-id="310ee-110">[out] A pointer to the [IEnumWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-ienumwbemclassobject) instance to be cloned.</span></span>

`strUser`\
<span data-ttu-id="310ee-111">de El nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="310ee-111">[in] The user name.</span></span> <span data-ttu-id="310ee-112">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="310ee-112">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strPassword`\
<span data-ttu-id="310ee-113">de La contraseña.</span><span class="sxs-lookup"><span data-stu-id="310ee-113">[in] The password.</span></span> <span data-ttu-id="310ee-114">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="310ee-114">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`strAuthority`\
<span data-ttu-id="310ee-115">de El nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="310ee-115">[in] The domain name of the user.</span></span> <span data-ttu-id="310ee-116">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="310ee-116">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

## <a name="return-value"></a><span data-ttu-id="310ee-117">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="310ee-117">Return value</span></span>

<span data-ttu-id="310ee-118">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="310ee-118">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="310ee-119">Constante</span><span class="sxs-lookup"><span data-stu-id="310ee-119">Constant</span></span>  |<span data-ttu-id="310ee-120">Value</span><span class="sxs-lookup"><span data-stu-id="310ee-120">Value</span></span>  |<span data-ttu-id="310ee-121">Descripción</span><span class="sxs-lookup"><span data-stu-id="310ee-121">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="310ee-122">0x80041001</span><span class="sxs-lookup"><span data-stu-id="310ee-122">0x80041001</span></span> | <span data-ttu-id="310ee-123">Se ha producido un error general.</span><span class="sxs-lookup"><span data-stu-id="310ee-123">There has been a general failure.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="310ee-124">0x80041008</span><span class="sxs-lookup"><span data-stu-id="310ee-124">0x80041008</span></span> | <span data-ttu-id="310ee-125">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="310ee-125">A parameter is invalid.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="310ee-126">0x80041006</span><span class="sxs-lookup"><span data-stu-id="310ee-126">0x80041006</span></span> | <span data-ttu-id="310ee-127">No hay suficiente memoria disponible para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="310ee-127">Not enough memory is available complete the operation.</span></span> |
| `WBEM_E_TRANSPORT_FAILURE` | <span data-ttu-id="310ee-128">0x80041015</span><span class="sxs-lookup"><span data-stu-id="310ee-128">0x80041015</span></span> | <span data-ttu-id="310ee-129">Error en el vínculo de llamada a procedimiento remoto (RPC) entre el proceso actual y WMI.</span><span class="sxs-lookup"><span data-stu-id="310ee-129">The remote procedure call (RPC) link between the current process and WMI has failed.</span></span> |
| `WBEM_S_NO_ERROR` | <span data-ttu-id="310ee-130">0</span><span class="sxs-lookup"><span data-stu-id="310ee-130">0</span></span> | <span data-ttu-id="310ee-131">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="310ee-131">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="310ee-132">Comentarios</span><span class="sxs-lookup"><span data-stu-id="310ee-132">Remarks</span></span>

<span data-ttu-id="310ee-133">Esta función contiene una llamada al método [IEnumWbemClassObject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) .</span><span class="sxs-lookup"><span data-stu-id="310ee-133">This function wraps a call to the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

<span data-ttu-id="310ee-134">Este método solo realiza una copia de "mejor esfuerzo".</span><span class="sxs-lookup"><span data-stu-id="310ee-134">This method makes only a "best effort" copy.</span></span> <span data-ttu-id="310ee-135">Debido a la naturaleza dinámica de muchos objetos CIM, es posible que el nuevo enumerador no enumere el mismo conjunto de objetos que el enumerador de origen.</span><span class="sxs-lookup"><span data-stu-id="310ee-135">Due to the dynamic nature of many CIM objects, it is possible that the new enumerator does not enumerate the same set of objects as the source enumerator.</span></span>

<span data-ttu-id="310ee-136">Si se produce un error en la llamada de función, puede obtener información de error adicional mediante una llamada a la función [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="310ee-136">If the function call fails, you can obtain additional error information by calling the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="example"></a><span data-ttu-id="310ee-137">Ejemplo</span><span class="sxs-lookup"><span data-stu-id="310ee-137">Example</span></span>

<span data-ttu-id="310ee-138">Para obtener un ejemplo, vea el método [IEnumWbemClassObject:: Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) .</span><span class="sxs-lookup"><span data-stu-id="310ee-138">For an example, see the [IEnumWbemClassObject::Clone](/windows/desktop/api/wbemcli/nf-wbemcli-ienumwbemclassobject-clone) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="310ee-139">Requisitos</span><span class="sxs-lookup"><span data-stu-id="310ee-139">Requirements</span></span>

 <span data-ttu-id="310ee-140">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="310ee-140">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="310ee-141">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="310ee-141">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="310ee-142">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="310ee-142">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="310ee-143">Consulte también</span><span class="sxs-lookup"><span data-stu-id="310ee-143">See also</span></span>

- [<span data-ttu-id="310ee-144">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="310ee-144">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
