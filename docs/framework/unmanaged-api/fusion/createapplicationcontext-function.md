---
title: CreateApplicationContext (Función)
ms.date: 03/30/2017
api_name:
- CreateApplicationContext
api_location:
- fusion.dll
api_type:
- DLLExport
f1_keywords:
- CreateApplicationContext
helpviewer_keywords:
- CreateApplicationContext function [.NET Framework fusion]
ms.assetid: 7bf8a141-b2c0-4058-9885-1cef7dcaa811
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a6b5aa78efcc19f1fc50c8e9bfc5105f9afd7d50
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/06/2019
ms.locfileid: "57495213"
---
# <a name="createapplicationcontext-function"></a>CreateApplicationContext (Función)
Esta función admite la infraestructura de .NET Framework y no está pensada para utilizarse directamente desde el código.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateApplicationContext (  
    [in]  IAssemblyName  *pName,  
    [out] LPPAPPLICATIONCONTEXT  *ppCtx  
 );  
```  
  
## <a name="parameters"></a>Parámetros  
 `pName`  
 [in] Un puntero a un nombre descriptivo.  
  
 `ppCtx`  
 [out] Un puntero a un contexto de la aplicación.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Fusion.h  
  
 **Biblioteca:** Incluye como recurso en el archivo Fusion.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [IAssemblyCache (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblycache-interface.md)
- [Funciones estáticas globales de la fusión](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
- [Caché global de ensamblados](../../../../docs/framework/app-domains/gac.md)
