---
title: "GetTypeLibInfo (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: GetTypeLibInfo
api_location: TlbRef.dll
api_type: DLLExport
f1_keywords: GetTypeLibInfo
helpviewer_keywords: GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type: apiref
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a5dc55a9538798b81dce9db02583c271b9f2ed54
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/21/2017
---
# <a name="gettypelibinfo-function"></a>GetTypeLibInfo (Función)
Devuelve información acerca de la biblioteca de tipos especificada mediante el examen de su [TLIBATTR](https://msdn.microsoft.com/library/ms221376\(v=vs.85\).aspx) estructura.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetTypeLibInfo(  
    [in]   LPWSTR     szFile,  
    [out]  GUID      *pTypeLibID,  
    [out]  LCID      *pTypeLibLCID,  
    [out]  SYSKIND   *pTypeLibPlatform,  
    [out]  USHORT    *pTypeLibMajorVer,  
    [out]  USHORT    *pTypeLibMinorVer  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `szFile`  
 [in] El nombre de archivo de la biblioteca de tipos.  
  
 `pTypeLibID`  
 [out] El GUID de la biblioteca de tipos.  
  
 `pTypeLibLCID`  
 [out] Identificador de localización de la biblioteca de tipos.  
  
 `pTypeLibPlatform`  
 [out] A [SYSKIND](https://msdn.microsoft.com/library/ms221272\(v=vs.85\).aspx) marca que identifica el sistema operativo de destino para la biblioteca de tipos. Los valores habituales son SYS_WIN32 y SYS_WIN64.  
  
 `pTypeLibMajorVer`  
 [out] El número de versión principal de la biblioteca de tipos. Por ejemplo, para la versión *x.y*, el número de versión principal es *x*.  
  
 `pTypeLibMinorVer`  
 [out] El número de versión secundaria de la biblioteca de tipos. Por ejemplo, para la versión *x.y*, el número de versión secundaria es *y*.  
  
## <a name="remarks"></a>Comentarios  
 El `GetTypeLibInfo` función llama a la [Tlbexp.exe (exportador de la biblioteca de tipos)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md). Esta herramienta genera una biblioteca de tipos que describe los tipos en un ensamblado de common language runtime (CLR).  
  
 Si cualquier parámetro es null, la función devuelve un `HRESULT` de `E_POINTER`. De lo contrario, devuelve `S_OK`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** TlbRef.h  
  
 **Biblioteca:** TlbRef.lib  
  
 **Versiones de .NET framework:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones auxiliares de Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [Función LoadTypeLibEx de la](https://msdn.microsoft.com/library/ms221249\(v=vs.85\).aspx)
