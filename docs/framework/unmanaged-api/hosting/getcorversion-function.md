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
ms.openlocfilehash: 23d68e8e4bbd87779e3b49f0c40f5a5ab9f5124f
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617222"
---
# <a name="getcorversion-function"></a>GetCORVersion (Función)
Devuelve el número de versión del Common Language Runtime (CLR) que se ejecuta en el proceso actual.  
  
 Esta función está en desuso en el .NET Framework 4.  
  
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
 Un puntero a un búfer en el que CLR devuelve una cadena que especifica la versión del Runtime que está cargada actualmente en el proceso. La cadena devuelta tiene el mismo formato que las cadenas que se pasan a [CorBindToRuntimeEx](corbindtoruntimeex-function.md), por ejemplo, "v 1.0.1216". Si el tiempo de ejecución aún no se ha cargado en el proceso, la función devuelve la información de directorio adecuada para la versión más reciente del motor en tiempo de ejecución instalada en el equipo.  
  
 `cchBuffer`  
 Número de caracteres `WCHAR` que se pueden mantener en `pbuffer` .  
  
 `dwLength`  
 Puntero al número de caracteres realmente devueltos en `pbuffer` . Si `pbuffer` es un puntero nulo, el tiempo de ejecución devuelve E_POINTER. Si el número de caracteres es mayor que la longitud de `pbuffer` , el tiempo de ejecución devuelve ERROR_INSUFFICIENT_BUFFER.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
