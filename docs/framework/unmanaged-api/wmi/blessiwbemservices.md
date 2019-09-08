---
title: Función BlessIWbemServices (referencia de la API no administrada)
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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 57ab5eb418b5f0a9175074c87837c7cac8936346
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70799048"
---
# <a name="blessiwbemservices-function"></a><span data-ttu-id="14df1-103">Función BlessIWbemServices</span><span class="sxs-lookup"><span data-stu-id="14df1-103">BlessIWbemServices function</span></span>
<span data-ttu-id="14df1-104">Indica si las credenciales de usuario permiten el acceso a la clase [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) especificada.</span><span class="sxs-lookup"><span data-stu-id="14df1-104">Indicates whether the user credentials permit access to the specified [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) class.</span></span>   
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="14df1-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="14df1-105">Syntax</span></span>  
  
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

## <a name="parameters"></a><span data-ttu-id="14df1-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="14df1-106">Parameters</span></span>

`pIWbemServices`\
<span data-ttu-id="14df1-107">de Puntero al objeto [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) para el que se requieren permisos.</span><span class="sxs-lookup"><span data-stu-id="14df1-107">[in] A pointer to the [IWbemServices](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemservices) object for which permissions are required.</span></span>

`strUser`\
<span data-ttu-id="14df1-108">de El nombre de usuario.</span><span class="sxs-lookup"><span data-stu-id="14df1-108">[in] The user name.</span></span>

`strPassword`\
<span data-ttu-id="14df1-109">de La contraseña asociada `strUser`a.</span><span class="sxs-lookup"><span data-stu-id="14df1-109">[in] The password associated with `strUser`.</span></span>

`strAuthority`\
<span data-ttu-id="14df1-110">de El nombre de dominio del usuario.</span><span class="sxs-lookup"><span data-stu-id="14df1-110">[in] The domain name of the user.</span></span> <span data-ttu-id="14df1-111">Vea la función [ConnectServerWmi](connectserverwmi.md) para obtener más información.</span><span class="sxs-lookup"><span data-stu-id="14df1-111">See the [ConnectServerWmi](connectserverwmi.md) function for more information.</span></span>

`impLevel`\
<span data-ttu-id="14df1-112">de Nivel de suplantación.</span><span class="sxs-lookup"><span data-stu-id="14df1-112">[in] The impersonation level.</span></span>

`authnLevel`\
<span data-ttu-id="14df1-113">de Nivel de autorización.</span><span class="sxs-lookup"><span data-stu-id="14df1-113">[in] The authorization level.</span></span>

## <a name="return-value"></a><span data-ttu-id="14df1-114">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="14df1-114">Return value</span></span>

<span data-ttu-id="14df1-115">Los siguientes valores devueltos por esta función se definen en el archivo de encabezado *WinError. h* , o bien se pueden definir como constantes en el código:</span><span class="sxs-lookup"><span data-stu-id="14df1-115">The following values returned by this function are defined in the *WinError.h* header file, or you can define them as constants in your code:</span></span>

|<span data-ttu-id="14df1-116">Constante</span><span class="sxs-lookup"><span data-stu-id="14df1-116">Constant</span></span>  |<span data-ttu-id="14df1-117">Valor</span><span class="sxs-lookup"><span data-stu-id="14df1-117">Value</span></span>  |<span data-ttu-id="14df1-118">DESCRIPCIÓN</span><span class="sxs-lookup"><span data-stu-id="14df1-118">Description</span></span>  |
|---------|---------|---------|
| `E_INVALIDARG` | <span data-ttu-id="14df1-119">0x80070057</span><span class="sxs-lookup"><span data-stu-id="14df1-119">0x80070057</span></span> | <span data-ttu-id="14df1-120">Uno o varios argumentos no son válidos.</span><span class="sxs-lookup"><span data-stu-id="14df1-120">One or more arguments are invalid.</span></span> |
| `E_POINTER` | <span data-ttu-id="14df1-121">0x80004003</span><span class="sxs-lookup"><span data-stu-id="14df1-121">0x80004003</span></span> | <span data-ttu-id="14df1-122">El valor de `pIWbemServices` es `null`.</span><span class="sxs-lookup"><span data-stu-id="14df1-122">`pIWbemServices` is `null`.</span></span> | 
| `E_FAIL` | <span data-ttu-id="14df1-123">0x80000008</span><span class="sxs-lookup"><span data-stu-id="14df1-123">0x80000008</span></span> | <span data-ttu-id="14df1-124">Se ha producido un error no especificado.</span><span class="sxs-lookup"><span data-stu-id="14df1-124">An unspecified error has occurred.</span></span> |
| `E_OUTOFMEMORY` | <span data-ttu-id="14df1-125">0x80000002</span><span class="sxs-lookup"><span data-stu-id="14df1-125">0x80000002</span></span> | <span data-ttu-id="14df1-126">No hay suficiente memoria disponible para realizar la operación.</span><span class="sxs-lookup"><span data-stu-id="14df1-126">Insufficient memory is available to perform the operation.</span></span> | 
| `S_OK` | <span data-ttu-id="14df1-127">0</span><span class="sxs-lookup"><span data-stu-id="14df1-127">0</span></span> | <span data-ttu-id="14df1-128">La llamada de función se realizó correctamente.</span><span class="sxs-lookup"><span data-stu-id="14df1-128">The function call was successful.</span></span> | 

## <a name="requirements"></a><span data-ttu-id="14df1-129">Requisitos</span><span class="sxs-lookup"><span data-stu-id="14df1-129">Requirements</span></span>  

 <span data-ttu-id="14df1-130">**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="14df1-130">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="14df1-131">**Encabezado**: WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="14df1-131">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="14df1-132">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="14df1-132">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="14df1-133">Vea también</span><span class="sxs-lookup"><span data-stu-id="14df1-133">See also</span></span>

- [<span data-ttu-id="14df1-134">WMI y contadores de rendimiento (referencia de la API no administrada)</span><span class="sxs-lookup"><span data-stu-id="14df1-134">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
