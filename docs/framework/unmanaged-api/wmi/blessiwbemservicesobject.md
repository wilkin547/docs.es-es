---
title: BlessIWbemServicesObject (función) (referencia de API no administrada)
description: BlessIWbemServicesObject (función) indica si las credenciales de usuario permiten el acceso a un objeto IWbemServices
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a561c5af868968624ee9ee81050d87b17c4591be
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/23/2019
ms.locfileid: "54624423"
---
# <a name="blessiwbemservicesobject-function"></a><span data-ttu-id="7050a-103">BlessIWbemServicesObject (función)</span><span class="sxs-lookup"><span data-stu-id="7050a-103">BlessIWbemServicesObject function</span></span>
<span data-ttu-id="7050a-104">Indica si las credenciales de usuario permiten el acceso a un determinado [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) objeto.</span><span class="sxs-lookup"><span data-stu-id="7050a-104">Indicates whether the user credentials permit access to a specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="7050a-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="7050a-105">Syntax</span></span>  
  
```  
HRESULT BlessIWbemServicesObject (
   [in] IUnknown* pIUnknown,
   [in] BSTR strUser, 
   [in] BSTR strPassword, 
   [in] BSTR strAuthority, 
   [in] DWORD impLevel, 
   [in] DWORD authnLevel
);
```  

## <a name="parameters"></a><span data-ttu-id="7050a-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="7050a-106">Parameters</span></span>

`pIWbemServices`  
<span data-ttu-id="7050a-107">[in] Un puntero a un objeto de servicio WMI.</span><span class="sxs-lookup"><span data-stu-id="7050a-107">[in] A pointer to a WMI service object.</span></span>

`strUser`  
<span data-ttu-id="7050a-108">[in] El nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="7050a-108">[in] The user name.</span></span>

`strPassword`  
<span data-ttu-id="7050a-109">[in] La contraseña asociada con `strUser`.</span><span class="sxs-lookup"><span data-stu-id="7050a-109">[in] The password associated with `strUser`.</span></span>

<span data-ttu-id="7050a-110">`strAuthority` [in] El nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="7050a-110">`strAuthority` [in] The domain name of the user.</span></span> <span data-ttu-id="7050a-111">Consulte la [ConnectServerWmi](connectserverwmi.md) función para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="7050a-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

<span data-ttu-id="7050a-112">`impLevel` [in] El nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="7050a-112">`impLevel` [in] The impersonation level.</span></span>

<span data-ttu-id="7050a-113">`authnLevel` [in] El nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="7050a-113">`authnLevel` [in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="7050a-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="7050a-114">Return value</span></span>

<span data-ttu-id="7050a-115">Los siguientes valores devueltos por esta función se definen en el *WinError.h* archivo de encabezado, también puede definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="7050a-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="7050a-116">Constante</span><span class="sxs-lookup"><span data-stu-id="7050a-116">Constant</span></span>  |<span data-ttu-id="7050a-117">Valor</span><span class="sxs-lookup"><span data-stu-id="7050a-117">Value</span></span>  |<span data-ttu-id="7050a-118">Descripción</span><span class="sxs-lookup"><span data-stu-id="7050a-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="7050a-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="7050a-119">0x80070057</span></span> | <span data-ttu-id="7050a-120">Uno o más argumentos no son válidos.</span><span class="sxs-lookup"><span data-stu-id="7050a-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="7050a-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="7050a-121">0x80004003</span></span> | <span data-ttu-id="7050a-122">El valor de `pIWbemServices` es `null`.</span><span class="sxs-lookup"><span data-stu-id="7050a-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="7050a-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="7050a-123">0x80000008</span></span> | <span data-ttu-id="7050a-124">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="7050a-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="7050a-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="7050a-125">0x80000002</span></span> | <span data-ttu-id="7050a-126">No hay memoria suficiente está disponible para realizar la operación.</span><span class="sxs-lookup"><span data-stu-id="7050a-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="7050a-127">0</span><span class="sxs-lookup"><span data-stu-id="7050a-127">0</span></span> | <span data-ttu-id="7050a-128">La llamada de función fue correcta.</span><span class="sxs-lookup"><span data-stu-id="7050a-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="7050a-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="7050a-129">Requirements</span></span>  
 <span data-ttu-id="7050a-130">**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="7050a-130">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7050a-131">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="7050a-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="7050a-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="7050a-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="7050a-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="7050a-133">See also</span></span>
- [<span data-ttu-id="7050a-134">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="7050a-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
