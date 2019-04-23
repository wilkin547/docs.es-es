---
title: GetMethodOrigin (función) (referencia de API no administrada)
description: GetMethodOrigin (función) determina la clase en el que se declara un método.
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 193caa894b8697a65e8821c01a63dde9cc5b5ccc
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153717"
---
# <a name="getmethodorigin-function"></a><span data-ttu-id="3b1bc-103">Función GetMethodOrigin</span><span class="sxs-lookup"><span data-stu-id="3b1bc-103">GetMethodOrigin function</span></span>
<span data-ttu-id="3b1bc-104">Determina la clase en la que se declara un método.</span><span class="sxs-lookup"><span data-stu-id="3b1bc-104">Determines the class in which a method is declared.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
    
## <a name="syntax"></a><span data-ttu-id="3b1bc-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="3b1bc-105">Syntax</span></span>  
  
```  
HRESULT GetMethodOrigin (
   [in] int                 vFunc, 
   [in] IWbemClassObject*   ptr, 
   [in] LPCWSTR             wszMethodName,
   [out] BSTR*              pstrClassName
); 
```  

## <a name="parameters"></a><span data-ttu-id="3b1bc-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="3b1bc-106">Parameters</span></span>

`vFunc`  
<span data-ttu-id="3b1bc-107">[in] Este parámetro se usa.</span><span class="sxs-lookup"><span data-stu-id="3b1bc-107">[in] This parameter is unused.</span></span>

`ptr`  
<span data-ttu-id="3b1bc-108">[in] Un puntero a un [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instancia.</span><span class="sxs-lookup"><span data-stu-id="3b1bc-108">[in] A pointer to an [IWbemClassObject](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemclassobject) instance.</span></span>

`wszMethodName`  
<span data-ttu-id="3b1bc-109">[in] El nombre del método para el objeto cuya clase propietaria se solicita.</span><span class="sxs-lookup"><span data-stu-id="3b1bc-109">[in] The name of the method for the object whose owning class is being requested.</span></span> 

`pstrClassName`  
<span data-ttu-id="3b1bc-110">[out] Recibe el nombre de la clase que posee el método.</span><span class="sxs-lookup"><span data-stu-id="3b1bc-110">[out] Receives the name of the class that owns the method.</span></span>

## <a name="return-value"></a><span data-ttu-id="3b1bc-111">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="3b1bc-111">Return value</span></span>

<span data-ttu-id="3b1bc-112">Los siguientes valores devueltos por esta función se definen en el *WbemCli.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="3b1bc-112">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="3b1bc-113">Constante</span><span class="sxs-lookup"><span data-stu-id="3b1bc-113">Constant</span></span>  |<span data-ttu-id="3b1bc-114">Valor</span><span class="sxs-lookup"><span data-stu-id="3b1bc-114">Value</span></span>  |<span data-ttu-id="3b1bc-115">Descripción</span><span class="sxs-lookup"><span data-stu-id="3b1bc-115">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="3b1bc-116">0x80041002</span><span class="sxs-lookup"><span data-stu-id="3b1bc-116">0x80041002</span></span> | <span data-ttu-id="3b1bc-117">No se encontró el método especificado.</span><span class="sxs-lookup"><span data-stu-id="3b1bc-117">The specified method was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="3b1bc-118">0x80041008</span><span class="sxs-lookup"><span data-stu-id="3b1bc-118">0x80041008</span></span> | <span data-ttu-id="3b1bc-119">Uno o más parámetros no son válidos.</span><span class="sxs-lookup"><span data-stu-id="3b1bc-119">One or more parameters are not valid.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="3b1bc-120">0</span><span class="sxs-lookup"><span data-stu-id="3b1bc-120">0</span></span> | <span data-ttu-id="3b1bc-121">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="3b1bc-121">The function call was successful.</span></span>  |
  
## <a name="remarks"></a><span data-ttu-id="3b1bc-122">Comentarios</span><span class="sxs-lookup"><span data-stu-id="3b1bc-122">Remarks</span></span>

<span data-ttu-id="3b1bc-123">Esta función contiene una llamada a la [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) método.</span><span class="sxs-lookup"><span data-stu-id="3b1bc-123">This function wraps a call to the [IWbemClassObject::GetMethodOrigin](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemclassobject-getmethod) method.</span></span>

<span data-ttu-id="3b1bc-124">Porque una clase puede heredar los métodos de una o más clases bases, los desarrolladores a menudo desean determinar la clase en el que se define un método determinado.</span><span class="sxs-lookup"><span data-stu-id="3b1bc-124">Because a class can inherit methods from one or more base classes, developers often want to determine the class in which a given method is defined.</span></span>

<span data-ttu-id="3b1bc-125">El `pstrClassName` parámetro no debe apuntar a una `BSTR` antes de llama a la función porque se trata de un `out` parámetro; este puntero no se desasigna cuando la función vuelve.</span><span class="sxs-lookup"><span data-stu-id="3b1bc-125">The `pstrClassName` parameter must not point to a valid `BSTR` before the function is called because this is an `out` parameter; this pointer is not deallocated after the function returns.</span></span>

## <a name="requirements"></a><span data-ttu-id="3b1bc-126">Requisitos</span><span class="sxs-lookup"><span data-stu-id="3b1bc-126">Requirements</span></span>  
<span data-ttu-id="3b1bc-127">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="3b1bc-127">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="3b1bc-128">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="3b1bc-128">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="3b1bc-129">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="3b1bc-129">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3b1bc-130">Vea también</span><span class="sxs-lookup"><span data-stu-id="3b1bc-130">See also</span></span>

- [<span data-ttu-id="3b1bc-131">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="3b1bc-131">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
