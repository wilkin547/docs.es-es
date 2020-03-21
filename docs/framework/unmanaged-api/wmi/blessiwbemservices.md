---
title: Función BlessIWbemServices (Referencia de API no administrada)
description: La función BlessIWbemServices indica si las credenciales de usuario permiten el acceso a una clase IWbemServices.
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
ms.openlocfilehash: 4b15af840cc00b3ec261604db4f3625c6b975d3e
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176869"
---
# <a name="blessiwbemservices-function"></a><span data-ttu-id="ea15d-103">Función BlessIWbemServices</span><span class="sxs-lookup"><span data-stu-id="ea15d-103">BlessIWbemServices function</span></span>
<span data-ttu-id="ea15d-104">Indica si las credenciales de usuario permiten el acceso a la clase [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) especificada.</span><span class="sxs-lookup"><span data-stu-id="ea15d-104">Indicates whether the user credentials permit access to the specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) class.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="ea15d-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="ea15d-105">Syntax</span></span>  
  
```cpp
HRESULT BlessIWbemServices (
   [in] IWbemServices* pIWbemServices,
   [in] BSTR strUser,
   [in] BSTR strPassword,
   [in] BSTR strAuthority,
   [in] DWORD impLevel,
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a><span data-ttu-id="ea15d-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="ea15d-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="ea15d-107">[en] Puntero al objeto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) para el que se requieren permisos.</span><span class="sxs-lookup"><span data-stu-id="ea15d-107">[in] A pointer to the [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object for which permissions are required.</span></span>

`strUser`\
<span data-ttu-id="ea15d-108">[en] El nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="ea15d-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="ea15d-109">[en] La contraseña `strUser`asociada a .</span><span class="sxs-lookup"><span data-stu-id="ea15d-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="ea15d-110">[en] El nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="ea15d-110">[in] The domain name of the user.</span></span> <span data-ttu-id="ea15d-111">Consulte la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="ea15d-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="ea15d-112">[en] El nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="ea15d-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="ea15d-113">[en] El nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="ea15d-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="ea15d-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="ea15d-114">Return value</span></span>

<span data-ttu-id="ea15d-115">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WinError.h* o puede definirlos como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="ea15d-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="ea15d-116">Constante</span><span class="sxs-lookup"><span data-stu-id="ea15d-116">Constant</span></span>  |<span data-ttu-id="ea15d-117">Value</span><span class="sxs-lookup"><span data-stu-id="ea15d-117">Value</span></span>  |<span data-ttu-id="ea15d-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="ea15d-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="ea15d-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="ea15d-119">0x80070057</span></span> | <span data-ttu-id="ea15d-120">Uno o más argumentos no son válidos.</span><span class="sxs-lookup"><span data-stu-id="ea15d-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="ea15d-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="ea15d-121">0x80004003</span></span> | <span data-ttu-id="ea15d-122">`pIWbemServices` es `null`.</span><span class="sxs-lookup"><span data-stu-id="ea15d-122">`pIWbemServices` is `null`.</span></span> |
| `E_FAIL` | <span data-ttu-id="ea15d-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="ea15d-123">0x80000008</span></span> | <span data-ttu-id="ea15d-124">Error no especificado.</span><span class="sxs-lookup"><span data-stu-id="ea15d-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="ea15d-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="ea15d-125">0x80000002</span></span> | <span data-ttu-id="ea15d-126">Hay suficiente memoria disponible para realizar la operación.</span><span class="sxs-lookup"><span data-stu-id="ea15d-126">Insufficient memory is available to perform the operation.</span></span> |
| `S_OK` | <span data-ttu-id="ea15d-127">0</span><span class="sxs-lookup"><span data-stu-id="ea15d-127">0</span></span> | <span data-ttu-id="ea15d-128">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="ea15d-128">The function call was successful.</span></span> |

## <a name="requirements"></a><span data-ttu-id="ea15d-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="ea15d-129">Requirements</span></span>  

 <span data-ttu-id="ea15d-130">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="ea15d-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ea15d-131">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="ea15d-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="ea15d-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="ea15d-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ea15d-133">Consulte también</span><span class="sxs-lookup"><span data-stu-id="ea15d-133">See also</span></span>

- [<span data-ttu-id="ea15d-134">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="ea15d-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
