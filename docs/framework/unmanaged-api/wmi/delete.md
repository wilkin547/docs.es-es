---
title: Función Delete (referencia de la API no administrada)
description: La función Delete elimina la propiedad especificada y todos sus calificadores de una definición de clase CIM.
ms.date: 11/06/2017
api_name:
- Delete
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- Delete
helpviewer_keywords:
- Delete function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a1bf9bd5d93d1affee649588138456269411d280
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70798672"
---
# <a name="delete-function"></a><span data-ttu-id="c3fe6-103">Función Delete</span><span class="sxs-lookup"><span data-stu-id="c3fe6-103">Delete function</span></span>

<span data-ttu-id="c3fe6-104">Elimina la propiedad especificada y todos sus calificadores de una definición de clase CIM.</span><span class="sxs-lookup"><span data-stu-id="c3fe6-104">Deletes the specified property and all of its qualifiers from a CIM class definition.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="c3fe6-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="c3fe6-105">Syntax</span></span>

```cpp
HRESULT Delete (
   [in] int               vFunc,
   [in] IWbemClassObject* ptr,
   [in] LPCWSTR           wszName
);
```

## <a name="parameters"></a><span data-ttu-id="c3fe6-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="c3fe6-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="c3fe6-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="c3fe6-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="c3fe6-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="c3fe6-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszName`\
<span data-ttu-id="c3fe6-109">de Nombre de la propiedad que se va a eliminar.</span><span class="sxs-lookup"><span data-stu-id="c3fe6-109">[in] The name of the property to delete.</span></span> <span data-ttu-id="c3fe6-110">`wszName`debe ser un puntero a un válido `LPCWSTR`.</span><span class="sxs-lookup"><span data-stu-id="c3fe6-110">`wszName` must be a pointer to a valid `LPCWSTR`.</span></span>

## <a name="return-value"></a><span data-ttu-id="c3fe6-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="c3fe6-111">Return value</span></span>

<span data-ttu-id="c3fe6-112">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="c3fe6-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="c3fe6-113">Constante</span><span class="sxs-lookup"><span data-stu-id="c3fe6-113">Constant</span></span>  |<span data-ttu-id="c3fe6-114">Value</span><span class="sxs-lookup"><span data-stu-id="c3fe6-114">Value</span></span>  |<span data-ttu-id="c3fe6-115">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="c3fe6-115">Description</span></span>  |
|---------|---------|---------|
| `WBEM_E_FAILED` | <span data-ttu-id="c3fe6-116">0x80041001</span><span class="sxs-lookup"><span data-stu-id="c3fe6-116">0x80041001</span></span> | <span data-ttu-id="c3fe6-117">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="c3fe6-117">An unspecified error has occurred.</span></span> |
| `WBEM_E_INVALID_OPERATION` | <span data-ttu-id="c3fe6-118">0x80041016</span><span class="sxs-lookup"><span data-stu-id="c3fe6-118">0x80041016</span></span> | <span data-ttu-id="c3fe6-119">No se puede eliminar la propiedad.</span><span class="sxs-lookup"><span data-stu-id="c3fe6-119">The property cannot be deleted.</span></span> |
| `WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="c3fe6-120">0x80041008</span><span class="sxs-lookup"><span data-stu-id="c3fe6-120">0x80041008</span></span> | <span data-ttu-id="c3fe6-121">`wszName` no es válido.</span><span class="sxs-lookup"><span data-stu-id="c3fe6-121">`wszName` is invalid.</span></span> |
| `WBEM_E_NOT_FOUND` | <span data-ttu-id="c3fe6-122">0x80041002</span><span class="sxs-lookup"><span data-stu-id="c3fe6-122">0x80041002</span></span> | <span data-ttu-id="c3fe6-123">La propiedad especificada no existe.</span><span class="sxs-lookup"><span data-stu-id="c3fe6-123">The specified property does not exist.</span></span> |
| `WBEM_E_OUT_OF_MEMORY` | <span data-ttu-id="c3fe6-124">0x80041006</span><span class="sxs-lookup"><span data-stu-id="c3fe6-124">0x80041006</span></span> | <span data-ttu-id="c3fe6-125">No hay suficiente memoria para completar la operación.</span><span class="sxs-lookup"><span data-stu-id="c3fe6-125">There is not enough memory to complete the operation.</span></span> |
| `WBEM_E_PROPAGATED_PROPERTY` | <span data-ttu-id="c3fe6-126">0x8004101c</span><span class="sxs-lookup"><span data-stu-id="c3fe6-126">0x8004101c</span></span> | <span data-ttu-id="c3fe6-127">La propiedad se hereda de una clase base.</span><span class="sxs-lookup"><span data-stu-id="c3fe6-127">The property is inherited from a base class.</span></span> |
| `WBEM_E_SYSTEM_PROPERTY` | | <span data-ttu-id="c3fe6-128">La propiedad es una propiedad del sistema.</span><span class="sxs-lookup"><span data-stu-id="c3fe6-128">The property is a system property.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="c3fe6-129">0</span><span class="sxs-lookup"><span data-stu-id="c3fe6-129">0</span></span> | <span data-ttu-id="c3fe6-130">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="c3fe6-130">The function call was successful.</span></span>  |
| `WBEM_E_RESET_TO_DEFAULT` | <span data-ttu-id="c3fe6-131">0x80041030</span><span class="sxs-lookup"><span data-stu-id="c3fe6-131">0x80041030</span></span> | <span data-ttu-id="c3fe6-132">La función eliminó un valor predeterminado de invalidación para la clase actual.</span><span class="sxs-lookup"><span data-stu-id="c3fe6-132">The function deleted an override default value for the current class.</span></span> <span data-ttu-id="c3fe6-133">Se ha reactivado el valor predeterminado de esta propiedad en la clase primaria.</span><span class="sxs-lookup"><span data-stu-id="c3fe6-133">The default value for this property in the parent class has been reactivated.</span></span> |

## <a name="remarks"></a><span data-ttu-id="c3fe6-134">Comentarios</span><span class="sxs-lookup"><span data-stu-id="c3fe6-134">Remarks</span></span>

<span data-ttu-id="c3fe6-135">Esta función contiene una llamada al método [IWbemClassObject::D iminar](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) .</span><span class="sxs-lookup"><span data-stu-id="c3fe6-135">This function wraps a call to the [IWbemClassObject::Delete](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-delete) method.</span></span>

## <a name="requirements"></a><span data-ttu-id="c3fe6-136">Requisitos</span><span class="sxs-lookup"><span data-stu-id="c3fe6-136">Requirements</span></span>

<span data-ttu-id="c3fe6-137">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="c3fe6-137">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

<span data-ttu-id="c3fe6-138">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="c3fe6-138">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="c3fe6-139">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="c3fe6-139">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="c3fe6-140">Vea también</span><span class="sxs-lookup"><span data-stu-id="c3fe6-140">See also</span></span>

- [<span data-ttu-id="c3fe6-141">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="c3fe6-141">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
