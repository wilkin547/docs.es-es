---
title: BlessIWbemServices (función) (referencia de API no administrada)
description: BlessIWbemServices (función) indica si las credenciales de usuario permiten el acceso a una clase IWbemServices.
ms.date: 11/06/2017
api_name:
- BlessIWbemServices
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- BlessIWbemServices
helpviewer_keywords:
- BlessIWbemServices function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a65c3c14507b2520c69875a1bc101ce826ace7ba
ms.sourcegitcommit: a885cc8c3e444ca6471348893d5373c6e9e49a47
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/06/2018
ms.locfileid: "44041413"
---
# <a name="blessiwbemservices-function"></a><span data-ttu-id="92304-103">BlessIWbemServices (función)</span><span class="sxs-lookup"><span data-stu-id="92304-103">BlessIWbemServices function</span></span>
<span data-ttu-id="92304-104">Indica si las credenciales de usuario permiten el acceso a la especificada [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) clase.</span><span class="sxs-lookup"><span data-stu-id="92304-104">Indicates whether the user credentials permit access to the specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) class.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="92304-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="92304-105">Syntax</span></span>  
  
```  
HRESULT BlessIWbemServices (
   [in] IWbemServices* pIWbemServices,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a><span data-ttu-id="92304-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="92304-106">Parameters</span></span>

`pIWbemServices`  
<span data-ttu-id="92304-107">[in] Un puntero a la [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) para el que se requieren permisos de objeto.</span><span class="sxs-lookup"><span data-stu-id="92304-107">[in] A pointer to the [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object for which permissions are required.</span></span>

`strUser`  
<span data-ttu-id="92304-108">[in] El nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="92304-108">[in] The user name.</span></span>

`strPassword`  
<span data-ttu-id="92304-109">[in] La contraseña asociada con `strUser`.</span><span class="sxs-lookup"><span data-stu-id="92304-109">[in] The password associated with `strUser`.</span></span>

<span data-ttu-id="92304-110">`strAuthority` [in] El nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="92304-110">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="92304-111">Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="92304-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="92304-112">`impLevel` [in] El nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="92304-112">`impLevel` [in] The impersonation level.</span></span>

<span data-ttu-id="92304-113">`authnLevel` [in] El nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="92304-113">`authnLevel` [in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="92304-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="92304-114">Return value</span></span>

<span data-ttu-id="92304-115">Los siguientes valores devueltos por esta función se definen en el *WinError.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="92304-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="92304-116">Constante</span><span class="sxs-lookup"><span data-stu-id="92304-116">Constant</span></span>  |<span data-ttu-id="92304-117">Valor</span><span class="sxs-lookup"><span data-stu-id="92304-117">Value</span></span>  |<span data-ttu-id="92304-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="92304-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="92304-119">0 x 80070057</span><span class="sxs-lookup"><span data-stu-id="92304-119">0x80070057</span></span> | <span data-ttu-id="92304-120">Uno o más argumentos no son válidos.</span><span class="sxs-lookup"><span data-stu-id="92304-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="92304-121">0 x 80004003</span><span class="sxs-lookup"><span data-stu-id="92304-121">0x80004003</span></span> | <span data-ttu-id="92304-122">El valor de `pIWbemServices` es `null`.</span><span class="sxs-lookup"><span data-stu-id="92304-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="92304-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="92304-123">0x80000008</span></span> | <span data-ttu-id="92304-124">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="92304-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="92304-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="92304-125">0x80000002</span></span> | <span data-ttu-id="92304-126">No hay memoria suficiente está disponible para realizar la operación.</span><span class="sxs-lookup"><span data-stu-id="92304-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="92304-127">0</span><span class="sxs-lookup"><span data-stu-id="92304-127">0</span></span> | <span data-ttu-id="92304-128">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="92304-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="92304-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="92304-129">Requirements</span></span>  
 <span data-ttu-id="92304-130">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="92304-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="92304-131">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="92304-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="92304-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="92304-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="92304-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="92304-133">See also</span></span>  
[<span data-ttu-id="92304-134">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="92304-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
