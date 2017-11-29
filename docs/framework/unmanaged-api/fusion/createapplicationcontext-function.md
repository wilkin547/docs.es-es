---
title: "CreateApplicationContext (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateApplicationContext
api_location: fusion.dll
api_type: DLLExport
f1_keywords: CreateApplicationContext
helpviewer_keywords: CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type: apiref
caps.latest.revision: "7"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: c089c32d4bc8474168274186a9303d39976abfca
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="createapplicationcontext-function"></a>CreateApplicationContext (Función)
Esta función admite la infraestructura de .NET Framework y no está diseñada para utilizarse directamente desde el código.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pName`  
 [in] Un puntero a un nombre descriptivo.  
  
 `ppCtx`  
 [out] Un puntero a un contexto de la aplicación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Fusion.h  
  
 **Biblioteca:** incluye como recurso en Fusion.dll  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IAssemblyCache (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)  
 [Funciones estáticas globales de fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)  
 [Caché global de ensamblados](../../../../docs/framework/app-domains/gac.md)
