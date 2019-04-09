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
ms.openlocfilehash: 872164e2f48f1ef234b729b28aa9b1af1589c0fc
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59180952"
---
# <a name="getdemultiplexedstub-function"></a>Función GetDemultiplexedStub
Crea un receptor de reenvío de objetos para ayudar a un cliente a recibir llamadas asincrónicas desde la administración de Windows.
  
[!INCLUDE[internalonly-unmanaged](../../../../includes/internalonly-unmanaged.md)]
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetDemultiplexedStub (
   [in] IUnknown*    pObject, 
   [in] boolean      isLocal, 
   [out] IUnknown**  ppObject
); 
```  

## <a name="parameters"></a>Parámetros

`pObject`  
[in] Un puntero a la implementación de en el proceso del cliente de [IWbemObjectSink](/windows/desktop/api/wbemcli/nn-wbemcli-iwbemobjectsink).

`isLocal`  
[in] Una marca que indica si el evento es local (`true`); en caso contrario, `false`.

`ppObject`  
[out] Un receptor de reenviador de objeto que se va a ayudar a un cliente recibir llamadas asincrónicas de administración de Windows.

## <a name="return-value"></a>Valor devuelto

Si la función se realiza correctamente, el valor devuelto es `S_OK` (0).

Si se produce un error en la función, el valor devuelto es un código de error distinto de cero. Para obtener información de error extendida, llame a la [GetErrorInfo](geterrorinfo.md) función.
    
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: WMINet_Utils.idl  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v472plus](../../../../includes/net-current-v472plus.md)]  
  
## <a name="see-also"></a>Vea también

- [WMI y contadores de rendimiento (referencia de API no administrada)](index.md)
