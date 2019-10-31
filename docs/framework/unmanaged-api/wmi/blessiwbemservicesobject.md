---
title: Función BlessIWbemServicesObject (referencia de la API no administrada)
description: La función BlessIWbemServicesObject indica si las credenciales de usuario permiten el acceso a un objeto IWbemServices
ms.date: 11/06/2017
api_name:
- BlessIWbemServicesObject
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServicesObject
helpviewer_keywords:
- BlessIWbemServicesObject function [.NET WMI and performance counters]
topic_type:
- Reference
ms.openlocfilehash: f77ff394668a235dd63cf0cddf71ea418a28125b
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73141687"
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="4fe4e-103">Función BlessIWbemServicesObject</span><span class="sxs-lookup"><span data-stu-id="4fe4e-103">BlessIWbemServicesObject function</span></span>
<span data-ttu-id="4fe4e-104">Indica si las credenciales de usuario permiten el acceso a un objeto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) especificado.</span><span class="sxs-lookup"><span data-stu-id="4fe4e-104">Indicates whether the user credentials permit access to a specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object.</span></span> 

[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]

## <a name="syntax"></a><span data-ttu-id="4fe4e-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="4fe4e-105">Syntax</span></span>

```cpp
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```

## <a name="parameters"></a><span data-ttu-id="4fe4e-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="4fe4e-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="4fe4e-107">de Un puntero a un objeto de servicio WMI.</span><span class="sxs-lookup"><span data-stu-id="4fe4e-107">[in] A pointer to a WMI service object.</span></span>

`strUser`\
<span data-ttu-id="4fe4e-108">de El nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="4fe4e-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="4fe4e-109">de Contraseña asociada a `strUser`.</span><span class="sxs-lookup"><span data-stu-id="4fe4e-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="4fe4e-110">de El nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="4fe4e-110">[in] The domain name of the user.</span></span> <span data-ttu-id="4fe4e-111">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="4fe4e-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="4fe4e-112">de Nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="4fe4e-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="4fe4e-113">de Nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="4fe4e-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="4fe4e-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="4fe4e-114">Return value</span></span>

<span data-ttu-id="4fe4e-115">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WinError. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="4fe4e-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="4fe4e-116">Constante</span><span class="sxs-lookup"><span data-stu-id="4fe4e-116">Constant</span></span>  |<span data-ttu-id="4fe4e-117">Valor</span><span class="sxs-lookup"><span data-stu-id="4fe4e-117">Value</span></span>  |<span data-ttu-id="4fe4e-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="4fe4e-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="4fe4e-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="4fe4e-119">0x80070057</span></span> | <span data-ttu-id="4fe4e-120">Uno o varios argumentos no son válidos.</span><span class="sxs-lookup"><span data-stu-id="4fe4e-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="4fe4e-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="4fe4e-121">0x80004003</span></span> | <span data-ttu-id="4fe4e-122">El valor de `pIWbemServices` es `null`.</span><span class="sxs-lookup"><span data-stu-id="4fe4e-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="4fe4e-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="4fe4e-123">0x80000008</span></span> | <span data-ttu-id="4fe4e-124">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="4fe4e-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="4fe4e-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="4fe4e-125">0x80000002</span></span> | <span data-ttu-id="4fe4e-126">No hay suficiente memoria disponible para realizar la operación.</span><span class="sxs-lookup"><span data-stu-id="4fe4e-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="4fe4e-127">0</span><span class="sxs-lookup"><span data-stu-id="4fe4e-127">0</span></span> | <span data-ttu-id="4fe4e-128">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="4fe4e-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="4fe4e-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="4fe4e-129">Requirements</span></span>

 <span data-ttu-id="4fe4e-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="4fe4e-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>

 <span data-ttu-id="4fe4e-131">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="4fe4e-131">**Header:** WMINet_Utils.idl</span></span>

 <span data-ttu-id="4fe4e-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="4fe4e-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>

## <a name="see-also"></a><span data-ttu-id="4fe4e-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="4fe4e-133">See also</span></span>

- [<span data-ttu-id="4fe4e-134">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="4fe4e-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
