---
title: Función GetDemultiplexedStub (referencia de la API no administrada)
description: La función GetDemultiplexedStub crea un receptor de reenviador de objetos para ayudar a un cliente a recibir llamadas asincrónicas de la administración de Windows.
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
ms.openlocfilehash: f8f9b56268168bb16c476a9366facd17e8ac44e5
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730635"
---
# <a name="getdemultiplexedstub-function"></a><span data-ttu-id="e8d23-103">Función GetDemultiplexedStub</span><span class="sxs-lookup"><span data-stu-id="e8d23-103">GetDemultiplexedStub function</span></span>

<span data-ttu-id="e8d23-104">Crea un receptor de reenvío de objetos para ayudar a un cliente a recibir llamadas asincrónicas desde la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="e8d23-104">Creates an object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a><span data-ttu-id="e8d23-105">Sintaxis</span><span class="sxs-lookup"><span data-stu-id="e8d23-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject,
   [in] boolean      isLocal,
   [out] IUnknown**  ppObject
);
```  

## <a name="parameters"></a><span data-ttu-id="e8d23-106">Parámetros</span><span class="sxs-lookup"><span data-stu-id="e8d23-106">Parameters</span></span>

`pObject`  
<span data-ttu-id="e8d23-107">de Un puntero a la implementación en proceso del cliente de [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span><span class="sxs-lookup"><span data-stu-id="e8d23-107">[in] A pointer to the client's in-process implementation of [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).</span></span>

`isLocal`  
<span data-ttu-id="e8d23-108">de Marca que indica si el evento es local ( `true` ); en caso contrario, `false` .</span><span class="sxs-lookup"><span data-stu-id="e8d23-108">[in] A flag that indicates whether the event is local (`true`); otherwise, `false`.</span></span>

`ppObject`  
<span data-ttu-id="e8d23-109">enuncia Un receptor de reenviador de objetos para ayudar a un cliente a recibir llamadas asincrónicas de la administración de Windows.</span><span class="sxs-lookup"><span data-stu-id="e8d23-109">[out] A object forwarder sink to assist a client in receiving asynchronous calls from Windows Management.</span></span>

## <a name="return-value"></a><span data-ttu-id="e8d23-110">Valor devuelto</span><span class="sxs-lookup"><span data-stu-id="e8d23-110">Return value</span></span>

<span data-ttu-id="e8d23-111">Si la función se ejecuta correctamente, el valor devuelto es `S_OK` (0).</span><span class="sxs-lookup"><span data-stu-id="e8d23-111">If the function succeeds, the return value is `S_OK` (0).</span></span>

<span data-ttu-id="e8d23-112">Si se produce un error en la función, el valor devuelto es un código de error distinto de cero.</span><span class="sxs-lookup"><span data-stu-id="e8d23-112">If the function fails, the return value is a non-zero error code.</span></span> <span data-ttu-id="e8d23-113">Para obtener información de error extendida, llame a la función [GetErrorInfo](geterrorinfo.md) .</span><span class="sxs-lookup"><span data-stu-id="e8d23-113">To get extended error information, call the [GetErrorInfo](geterrorinfo.md) function.</span></span>

## <a name="requirements"></a><span data-ttu-id="e8d23-114">Requisitos</span><span class="sxs-lookup"><span data-stu-id="e8d23-114">Requirements</span></span>  

 <span data-ttu-id="e8d23-115">**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).</span><span class="sxs-lookup"><span data-stu-id="e8d23-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e8d23-116">**Encabezado:** WMINet_Utils. idl</span><span class="sxs-lookup"><span data-stu-id="e8d23-116">**Header:** WMINet_Utils.idl</span></span>  
  
 <span data-ttu-id="e8d23-117">**.NET Framework versiones:**[!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span><span class="sxs-lookup"><span data-stu-id="e8d23-117">**.NET Framework Versions:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e8d23-118">Consulte también</span><span class="sxs-lookup"><span data-stu-id="e8d23-118">See also</span></span>

- [<span data-ttu-id="e8d23-119">WMI y contadores de rendimiento (referencia de API no administrada)</span><span class="sxs-lookup"><span data-stu-id="e8d23-119">WMI and Performance Counters (Unmanaged API Reference)</span></span>](index.md)
