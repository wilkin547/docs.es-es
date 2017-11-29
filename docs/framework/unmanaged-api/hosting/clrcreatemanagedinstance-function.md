---
title: "ClrCreateManagedInstance (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
api_type: DLLExport
f1_keywords: ClrCreateManagedInstance
helpviewer_keywords: ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type: apiref
caps.latest.revision: "20"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 2d27a881f84121f0d096eae7c693dec5b674caec
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="clrcreatemanagedinstance-function"></a>ClrCreateManagedInstance (Función)
Crea una instancia del tipo administrado especificado.  
  
 Esta función está desusada en [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Utilizar la activación de COM para crear una instancia del tipo administrado o utilizar el hospedaje (consulte [de hospedaje de CLR agregadas Interfaces en .NET Framework 4 y 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,   
    [in]  REFIID   riid,   
    [out] void     **ppObject  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pTypeName`  
 [in] Un puntero al nombre del tipo de instancia que se solicita.  
  
 `riid`  
 [in] El `IID` del tipo de instancia que se solicita.  
  
 `ppObject`  
 [out] Un puntero a un puntero a una instancia del tipo administrado que se solicitó el llamador.  
  
## <a name="remarks"></a>Comentarios  
 Common language runtime debe estar ya cargado en un proceso. Por ejemplo, se puede cargar mediante el uso de una llamada a la [CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) funcionen antes de la `ClrCreateManagedInstance` función se invoca. Si el tiempo de ejecución no está cargado, `ClrCreateManagedInstance` primero intenta cargar v1.0.3705 del tiempo de ejecución. Si se produce un error, intenta cargar la versión más reciente del runtime.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE.h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)  
 [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
