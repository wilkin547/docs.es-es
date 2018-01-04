---
title: "ResolveTypeLib (Método)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ResolveTypeLib
api_location: tlbref.dll
f1_keywords: ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type: apiref
caps.latest.revision: "12"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: b668610f50c32373790130def17928b8b3b3d8b2
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="resolvetypelib-method"></a>ResolveTypeLib (Método)
Resuelve el nombre sencillo de una biblioteca de tipos mediante la devolución de su ruta de acceso completa.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `bstrSimpleName`  
 [in] A [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) que contiene el nombre sencillo de la biblioteca de tipos.  
  
 `tlbid`  
 [in] El GUID asignado a la biblioteca de tipos en el registro.  
  
 `lcid`  
 [in] Identificador de localización de la biblioteca de tipos.  
  
 `wMajorVersion`  
 [in] El número de versión principal de la biblioteca de tipos. Por ejemplo, para la versión *x.y*, el número de versión principal es *x*.  
  
 `wMinorVersion`  
 [in] El número de versión secundaria de la biblioteca de tipos. Por ejemplo, para la versión *x.y*, el número de versión secundaria es *y*.  
  
 `syskind`  
 [in] A [SYSKIND](http://msdn.microsoft.com/en-us/662048b2-59a8-48ca-9e4f-2f9a5306faa1) marca que identifica el entorno operativo. Los valores habituales son SYS_WIN32 y SYS_WIN64.  
  
 `pbstrResolvedTlbName`  
 [out] Un puntero a un [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) que contiene la ruta de acceso completa de la biblioteca de tipos con nombre en el `bstrSimpleName` parámetro.  
  
## <a name="remarks"></a>Comentarios  
 El `ResolveTypeLib` llama al método el [LoadTypeLibWithResolver (función)](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) durante [Tlbexp.exe (exportador de la biblioteca de tipos)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) de procesamiento.  
  
 Las implementaciones personalizadas de esta interfaz deben devolver un [BSTR](http://msdn.microsoft.com/en-us/1b2d7d2c-47af-4389-a6b6-b01b7e915228) que contiene la ruta de acceso completa de la biblioteca de tipos con nombre en el `bstrSimpleName` parámetro.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** TlbRef.idl, TlbRef.h  
  
 **Biblioteca:** TlbRef.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones auxiliares Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [LoadTypeLibEx de la](http://msdn.microsoft.com/en-us/56a7f9e1-810b-4a42-aa4d-691f4304f5ef)
