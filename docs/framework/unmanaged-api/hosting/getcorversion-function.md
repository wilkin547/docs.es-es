---
title: GetCORVersion (Función)
ms.date: 03/30/2017
api_name:
- GetCORVersion
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- DLLExport
f1_keywords:
- GetCORVersion
helpviewer_keywords:
- GetCORVersion function [.NET Framework hosting]
ms.assetid: 2f09cd37-bf3a-4cc5-87b0-adc42a7eed31
topic_type:
- apiref
ms.openlocfilehash: 1f40f27651d2d75cf2c3e4d7d1c21e1f47d402af
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178191"
---
# <a name="getcorversion-function"></a>GetCORVersion (Función)
Devuelve el número de versión de Common Language Runtime (CLR) que se ejecuta en el proceso actual.  
  
 Esta función ha quedado en desuso en .NET Framework 4.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCORVersion (  
    [in] LPWSTR  pbuffer,  
    [in]  DWORD   cchBuffer,
    [out] DWORD*  dwlength  
);
```  
  
## <a name="parameters"></a>Parámetros  
 `pbuffer`  
 Puntero a un búfer en el que CLR devuelve una cadena que especifica la versión del tiempo de ejecución que se carga actualmente en el proceso. La cadena devuelta toma la misma forma que las cadenas pasadas a [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md), por ejemplo, "v1.0.1216". Si el tiempo de ejecución aún no se ha cargado en el proceso, la función devuelve la información de directorio adecuada para la versión más reciente del tiempo de ejecución instalado en el equipo.  
  
 `cchBuffer`  
 El número de`WCHAR`caracteres ( s) que se pueden mantener en `pbuffer`.  
  
 `dwLength`  
 Puntero al número de caracteres `pbuffer`devueltos en . Si `pbuffer` es un puntero nulo, el tiempo de ejecución devuelve E_POINTER. Si el número de caracteres `pbuffer` es mayor, a continuación, la longitud de , el tiempo de ejecución devuelve ERROR_INSUFFICIENT_BUFFER.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MScorEE.h  
  
 **Biblioteca:** Mscoree.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
