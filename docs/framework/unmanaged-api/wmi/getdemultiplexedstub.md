---
title: Función GetDemultiplexedStub (referencia de API no administrada)
description: La función GetDemultiplexedStub crea un receptor de reenviador de objeto para ayudar a un cliente recibir llamadas asincrónicas de administración de Windows.
ms.date: 11/06/2017
api_name:
- GetDemultiplexedStub
api_location:
- WMINet_Utils.dll
api_type:
- DLLExport
f1_keywords:
- GetDemultiplexedStub
helpviewer_keywords:
- GetDemultiplexedStub function [.NET WMI and performance counters]
topic_type:
- Reference
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 4311a77c9159428bf7beacc99d4479acb28b91b6
ms.sourcegitcommit: 8c2ece71e54f46aef9a2153540d0bda7e74b19a9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/11/2018
ms.locfileid: "44361091"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="150f9-103">Función GetDemultiplexedStub</span><span class="sxs-lookup"><span data-stu-id="150f9-103">GetDemultiplexedStub function</span></span>
<span data-ttu-id="150f9-104">Crea un receptor de reenvío de objetos para ayudar a un cliente a recibir llamadas asincrónicas desde la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="150f9-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="150f9-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="150f9-105">Syntax</span></span>  
  
```  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a><span data-ttu-id="150f9-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="150f9-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="150f9-107">[in] Un puntero a la implementación de en el proceso del cliente de [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span><span class="sxs-lookup"><span data-stu-id="150f9-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="150f9-108">[in] Una marca que indica si el evento es local (`true`); en caso contrario, `false`.</span><span class="sxs-lookup"><span data-stu-id="150f9-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="150f9-109">[out] Un receptor de reenviador de objeto que se va a ayudar a un cliente recibir llamadas asincrónicas de administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="150f9-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="150f9-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="150f9-110">Return value</span></span>

<span data-ttu-id="150f9-111">Si la función se realiza correctamente, el valor devuelto es `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="150f9-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="150f9-112">Si se produce un error en la función, el valor devuelto es un código de error distinto de cero.</span><span class="sxs-lookup"><span data-stu-id="150f9-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="150f9-113">Para obtener información de error extendida, llame a la [GetErrorInfo](geterrorinfo.md) función.</span><span class="sxs-lookup"><span data-stu-id="150f9-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>
    
## <a name="requirements"></a><span data-ttu-id="150f9-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="150f9-114">Requirements</span></span>  
 <span data-ttu-id="150f9-115">**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="150f9-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="150f9-116">**Encabezado:** WMINet_Utils.idl</span><span class="sxs-lookup"><span data-stu-id="150f9-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="150f9-117">**Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="150f9-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="150f9-118">Vea también</span><span class="sxs-lookup"><span data-stu-id="150f9-118">See also</span></span>  
[<span data-ttu-id="150f9-119">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="150f9-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
