---
title: Función GetMethodQualifierSet (referencia de la API no administrada)
description: La función GetMethodQualifierSet recupera el conjunto de calificadores de un método.
ms.date: 11/06/2017
api_name:
- GetMethodQualifierSet
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodQualifierSet
helpviewer_keywords:
- GetMethodQualifierSet function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 1a36200fd214d013a10ed21c22e1f652de2cbf17
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73102574"
---
# <a name="getmethodqualifierset-function"></a><span data-ttu-id="3898a-103">Función GetMethodQualifierSet</span><span class="sxs-lookup"><span data-stu-id="3898a-103">GetMethodQualifierSet function</span></span>

<span data-ttu-id="3898a-104">Recupera el calificador establecido para un método específico.</span><span class="sxs-lookup"><span data-stu-id="3898a-104">Retrieves the qualifier set for a particular method.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="3898a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3898a-105">Syntax</span></span>

```cpp
HRESULT GetMethodQualifierSet (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethod,
   [out] IWbemQualifierSet  **ppQualSet
);
```

## <a name="parameters"></a><span data-ttu-id="3898a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3898a-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="3898a-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="3898a-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="3898a-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="3898a-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethod`\
<span data-ttu-id="3898a-109">de Nombre del método.</span><span class="sxs-lookup"><span data-stu-id="3898a-109">[in] The method  name.</span></span> <span data-ttu-id="3898a-110">`wszMethod` debe apuntar a un `LPCWSTR`válido.</span><span class="sxs-lookup"><span data-stu-id="3898a-110">`wszMethod` must point to a valid `LPCWSTR`.</span></span>

`ppQualSet`\
<span data-ttu-id="3898a-111">enuncia Recibe el puntero de interfaz que permite el acceso a los calificadores del método.</span><span class="sxs-lookup"><span data-stu-id="3898a-111">[out] Receives the interface pointer that allows access to the qualifiers of the method.</span></span> <span data-ttu-id="3898a-112">El valor de `ppQualSet` no puede ser `null`.</span><span class="sxs-lookup"><span data-stu-id="3898a-112">`ppQualSet` cannot be `null`.</span></span> <span data-ttu-id="3898a-113">Si se produce un error, no se devuelve un nuevo objeto y el puntero se establece para que apunte a `null`.</span><span class="sxs-lookup"><span data-stu-id="3898a-113">If an error occurs, a new object is not returned, and the pointer is set to point to `null`.</span></span>

## <a name="return-value"></a><span data-ttu-id="3898a-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3898a-114">Return value</span></span>

<span data-ttu-id="3898a-115">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="3898a-115">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3898a-116">Constante</span><span class="sxs-lookup"><span data-stu-id="3898a-116">Constant</span></span>  |<span data-ttu-id="3898a-117">Valor</span><span class="sxs-lookup"><span data-stu-id="3898a-117">Value</span></span>  |<span data-ttu-id="3898a-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="3898a-118">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="3898a-119">0x80041002</span><span class="sxs-lookup"><span data-stu-id="3898a-119">0x80041002</span></span> | <span data-ttu-id="3898a-120">El método especificado no existe.</span><span class="sxs-lookup"><span data-stu-id="3898a-120">The specified method does not exist.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3898a-121">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3898a-121">0x80041008</span></span> | <span data-ttu-id="3898a-122">Un parámetro es `null`.</span><span class="sxs-lookup"><span data-stu-id="3898a-122">A parameter is `null`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="3898a-123">0</span><span class="sxs-lookup"><span data-stu-id="3898a-123">0</span></span> | <span data-ttu-id="3898a-124">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="3898a-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="3898a-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3898a-125">Remarks</span></span>

<span data-ttu-id="3898a-126">Esta función contiene una llamada al método [IWbemClassObject:: GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) .</span><span class="sxs-lookup"><span data-stu-id="3898a-126">This function wraps a call to the [IWbemClassObject::GetMethodQualifierSet](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethodqualifierset) method.</span></span>

<span data-ttu-id="3898a-127">Solo se admite una llamada a esta función si el objeto actual es una definición de clase CIM.</span><span class="sxs-lookup"><span data-stu-id="3898a-127">A call to this function is supported only if the current object is a CIM class definition.</span></span> <span data-ttu-id="3898a-128">La manipulación de métodos no está disponible para los punteros [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) que señalan a las instancias CIM.</span><span class="sxs-lookup"><span data-stu-id="3898a-128">Method manipulation is not available for [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) pointers that point to CIM instances.</span></span>

<span data-ttu-id="3898a-129">Dado que cada método puede tener sus propios calificadores, el [puntero IWbemQualifierSet](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) permite al llamador agregar, editar o eliminar estos calificadores.</span><span class="sxs-lookup"><span data-stu-id="3898a-129">Because each method may have its own qualifiers, the [IWbemQualifierSet pointer](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemqualifierset) lets the caller add, edit, or delete these qualifiers.</span></span>

## <a name="requirements"></a><span data-ttu-id="3898a-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3898a-130">Requirements</span></span>

<span data-ttu-id="3898a-131">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3898a-131">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="3898a-132">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="3898a-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="3898a-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3898a-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="3898a-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="3898a-134">See also</span></span>

- [<span data-ttu-id="3898a-135">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="3898a-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
