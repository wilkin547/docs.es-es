---
title: Función GetMethodOrigin (referencia de la API no administrada)
description: La función GetMethodOrigin determina la clase en la que se declara un método.
ms.date: 11/06/2017
api_name:
- GetMethodOrigin
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetMethodOrigin
helpviewer_keywords:
- GetMethodOrigin function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: 434392ffb4d9124e319bcd9c42fdd340d3fec5b4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722783"
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="e6813-103">Función GetMethodOrigin</span><span class="sxs-lookup"><span data-stu-id="e6813-103">GetMethodOrigin function</span></span>

<span data-ttu-id="e6813-104">Determina la clase en la que se declara un método.</span><span class="sxs-lookup"><span data-stu-id="e6813-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="e6813-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e6813-105">Syntax</span></span>  
  
```cpp  
HRESULT GetMethodOrigin (
   [in] int                 vFunc,
   [in] IWbemClassObject*   ptr,
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
);
```  

## <a name="parameters"></a><span data-ttu-id="e6813-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e6813-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="e6813-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="e6813-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="e6813-108">de Puntero a una instancia de [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) .</span><span class="sxs-lookup"><span data-stu-id="e6813-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="e6813-109">de Nombre del método para el objeto cuya clase propietaria se está solicitando.</span><span class="sxs-lookup"><span data-stu-id="e6813-109">[in] The name of the method for the object whose owning class is being requested.</span></span>

`pstrClassName`  
<span data-ttu-id="e6813-110">enuncia Recibe el nombre de la clase a la que pertenece el método.</span><span class="sxs-lookup"><span data-stu-id="e6813-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="e6813-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e6813-111">Return value</span></span>

<span data-ttu-id="e6813-112">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="e6813-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="e6813-113">Constante</span><span class="sxs-lookup"><span data-stu-id="e6813-113">Constant</span></span>  |<span data-ttu-id="e6813-114">Value</span><span class="sxs-lookup"><span data-stu-id="e6813-114">Value</span></span>  |<span data-ttu-id="e6813-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="e6813-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="e6813-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="e6813-116">0x80041002</span></span> | <span data-ttu-id="e6813-117">No se encontró el método especificado.</span><span class="sxs-lookup"><span data-stu-id="e6813-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="e6813-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="e6813-118">0x80041008</span></span> | <span data-ttu-id="e6813-119">Uno o más parámetros no son válidos.</span><span class="sxs-lookup"><span data-stu-id="e6813-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="e6813-120">0</span><span class="sxs-lookup"><span data-stu-id="e6813-120">0</span></span> | <span data-ttu-id="e6813-121">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="e6813-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="e6813-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="e6813-122">Remarks</span></span>

<span data-ttu-id="e6813-123">Esta función contiene una llamada al método [IWbemClassObject:: GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) .</span><span class="sxs-lookup"><span data-stu-id="e6813-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="e6813-124">Dado que una clase puede heredar métodos de una o varias clases base, los desarrolladores suelen querer determinar la clase en la que se define un método determinado.</span><span class="sxs-lookup"><span data-stu-id="e6813-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="e6813-125">El `pstrClassName` parámetro no debe señalar a un válido `BSTR` antes de que se llame a la función porque es un `out` parámetro; este puntero no se desasigna después de que la función devuelva un error.</span><span class="sxs-lookup"><span data-stu-id="e6813-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="e6813-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e6813-126">Requirements</span></span>  

<span data-ttu-id="e6813-127">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e6813-127">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e6813-128">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="e6813-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e6813-129">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e6813-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6813-130">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e6813-130">See also</span></span>

- [<span data-ttu-id="e6813-131">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="e6813-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
