---
title: Función GetPropertyHandle (referencia de la API no administrada)
description: La función GetPropertyHandle devuelve un identificador único que identifica una propiedad.
ms.date: 11/06/2017
api_name:
- GetPropertyHandle
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetPropertyHandle
helpviewer_keywords:
- GetPropertyHandle function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d6dc2792b572aae30e9989c81967b86f340d7b83
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69038257"
---
# <a name="getpropertyhandle-function"></a><span data-ttu-id="8e968-103">Función GetPropertyHandle</span><span class="sxs-lookup"><span data-stu-id="8e968-103">GetPropertyHandle function</span></span>

<span data-ttu-id="8e968-104">Devuelve un controlador único que identifica una propiedad.</span><span class="sxs-lookup"><span data-stu-id="8e968-104">Returns a unique handle that identifies a property.</span></span>

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="8e968-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="8e968-105">Syntax</span></span>

```cpp
HRESULT GetPropertyHandle (
   [in] int                  vFunc,
   [in] IWbemObjectAccess*   ptr,
   [in] LPCWSTR              wszPropertyName,
   [out] CIMTYPE*            pType,
   [out] long*               pHandle
);
```

## <a name="parameters"></a><span data-ttu-id="8e968-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="8e968-106">Parameters</span></span>

`vFunc`\
<span data-ttu-id="8e968-107">de Este parámetro no se utiliza.</span><span class="sxs-lookup"><span data-stu-id="8e968-107">[in] This parameter is unused.</span></span>

`ptr`\
<span data-ttu-id="8e968-108">de Puntero a una instancia de [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) .</span><span class="sxs-lookup"><span data-stu-id="8e968-108">[in] A pointer to an [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) instance.</span></span>

`wszPropertyName`\
<span data-ttu-id="8e968-109">de Una cadena terminada en NULL de caracteres codificados en UTF16 que contiene el nombre de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8e968-109">[in] A null-terminated string of UTF16-encoded characters that contains the property name.</span></span>

`pType`\
<span data-ttu-id="8e968-110">enuncia Un puntero a un [`CIMTYPE`](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) miembro de enumeración que representa el tipo CIM de la propiedad.</span><span class="sxs-lookup"><span data-stu-id="8e968-110">[out] A pointer to a [`CIMTYPE`](/windows/win32/api/wbemcli/ne-wbemcli-cimtype_enumeration) enumeration member that represents the CIM type of the property.</span></span>

`pHandle`\
<span data-ttu-id="8e968-111">enuncia Un puntero a un entero que contiene el identificador de propiedad.</span><span class="sxs-lookup"><span data-stu-id="8e968-111">[out] A pointer to an integer that contains the property handle.</span></span>

## <a name="return-value"></a><span data-ttu-id="8e968-112">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="8e968-112">Return value</span></span>

<span data-ttu-id="8e968-113">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WbemCli. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="8e968-113">The following values returned by this function are defined in the *WbemCli.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="8e968-114">Constante</span><span class="sxs-lookup"><span data-stu-id="8e968-114">Constant</span></span>  |<span data-ttu-id="8e968-115">Valor</span><span class="sxs-lookup"><span data-stu-id="8e968-115">Value</span></span>  |<span data-ttu-id="8e968-116">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="8e968-116">Description</span></span>  |
|---------|---------|---------|
|`WBEM_E_NOT_FOUND` | <span data-ttu-id="8e968-117">0x80041002</span><span class="sxs-lookup"><span data-stu-id="8e968-117">0x80041002</span></span> | <span data-ttu-id="8e968-118">No se encontró el nombre de propiedad especificado.</span><span class="sxs-lookup"><span data-stu-id="8e968-118">The specified property name was not found.</span></span> |
|`WBEM_E_INVALID_PARAMETER` | <span data-ttu-id="8e968-119">0x80041008</span><span class="sxs-lookup"><span data-stu-id="8e968-119">0x80041008</span></span> | <span data-ttu-id="8e968-120">Un parámetro no es válido.</span><span class="sxs-lookup"><span data-stu-id="8e968-120">A parameter is not valid.</span></span> |
|`WBEM_E_NOT_SUPPORTED` | <span data-ttu-id="8e968-121">0x8004100c</span><span class="sxs-lookup"><span data-stu-id="8e968-121">0x8004100c</span></span> | <span data-ttu-id="8e968-122">La propiedad solicitada es de tipo `CIM_OBJECT` o `CIM_ARRAY`.</span><span class="sxs-lookup"><span data-stu-id="8e968-122">The requested property is of type are `CIM_OBJECT` or `CIM_ARRAY`.</span></span> |
|`WBEM_S_NO_ERROR` | <span data-ttu-id="8e968-123">0</span><span class="sxs-lookup"><span data-stu-id="8e968-123">0</span></span> | <span data-ttu-id="8e968-124">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="8e968-124">The function call was successful.</span></span>  |

## <a name="remarks"></a><span data-ttu-id="8e968-125">Comentarios</span><span class="sxs-lookup"><span data-stu-id="8e968-125">Remarks</span></span>

<span data-ttu-id="8e968-126">Esta función contiene una llamada al método [IWbemClassObject:: GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) .</span><span class="sxs-lookup"><span data-stu-id="8e968-126">This function wraps a call to the [IWbemClassObject::GetPropertyHandle](/windows/desktop/api/wbemcli/nf-wbemcli-iwbemobjectaccess-getpropertyhandle) method.</span></span>

<span data-ttu-id="8e968-127">Puede usar este identificador para identificar propiedades al utilizar métodos [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) para leer o escribir valores de propiedad.</span><span class="sxs-lookup"><span data-stu-id="8e968-127">You can use this handle to identify properties when using  [IWbemObjectAccess](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectaccess) methods to read or write property values.</span></span>

<span data-ttu-id="8e968-128">Los identificadores se pueden recuperar para las propiedades de todos los `CIM_OBJECT` tipos `CIM_ARRAY`de datos distintos de y.</span><span class="sxs-lookup"><span data-stu-id="8e968-128">Handles can be retrieved for properties of all data types other than `CIM_OBJECT` and `CIM_ARRAY`.</span></span> <span data-ttu-id="8e968-129">Los identificadores devueltos funcionan en todas las instancias de una clase.</span><span class="sxs-lookup"><span data-stu-id="8e968-129">Returned handles work across all instances of a class.</span></span>

## <a name="requirements"></a><span data-ttu-id="8e968-130">Requisitos</span><span class="sxs-lookup"><span data-stu-id="8e968-130">Requirements</span></span>

<span data-ttu-id="8e968-131">**Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="8e968-131">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>

<span data-ttu-id="8e968-132">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="8e968-132">**Header:** WMINet_Utils.idl</span></span>

<span data-ttu-id="8e968-133">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="8e968-133">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="8e968-134">Vea también</span><span class="sxs-lookup"><span data-stu-id="8e968-134">See also</span></span>

- [<span data-ttu-id="8e968-135">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="8e968-135">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
