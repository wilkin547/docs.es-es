---
title: GetTypeLibInfo (Función)
ms.date: 03/30/2017
api_name:
- GetTypeLibInfo
api_location:
- TlbRef.dll
api_type:
- DLLExport
f1_keywords:
- GetTypeLibInfo
helpviewer_keywords:
- GetTypeLibInfo function [.NET Framework]
ms.assetid: a1c4d165-9bdc-4ca8-940e-292d4ffcc338
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0ec28c581b8e6e0aff3a2765720b6e9795be931b
ms.sourcegitcommit: 6eac9a01ff5d70c6d18460324c016a3612c5e268
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/14/2018
ms.locfileid: "45615519"
---
# <a name="gettypelibinfo-function"></a>GetTypeLibInfo (Función)
Devuelve información acerca de la biblioteca de tipos especificado examinando su [TLIBATTR](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ns-oaidl-tagtlibattr) estructura.  
  
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
 [in] El nombre de la biblioteca de tipos de archivo.  
  
 `pTypeLibID`  
 [out] El GUID de la biblioteca de tipos.  
  
 `pTypeLibLCID`  
 [out] El identificador de localización de la biblioteca de tipos.  
  
 `pTypeLibPlatform`  
 [out] Un [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) marca que identifica el sistema operativo de destino para la biblioteca de tipos. Los valores habituales son SYS_WIN32 y SYS_WIN64.  
  
 `pTypeLibMajorVer`  
 [out] El número de versión principal de la biblioteca de tipos. Por ejemplo, para la versión *x.y*, el número de versión principal es *x*.  
  
 `pTypeLibMinorVer`  
 [out] El número de versión secundaria de la biblioteca de tipos. Por ejemplo, para la versión *x.y*, el número de versión secundaria es *y*.  
  
## <a name="remarks"></a>Comentarios  
 El `GetTypeLibInfo` llama a la función el [Tlbexp.exe (exportador de biblioteca)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md). Esta herramienta genera una biblioteca de tipos que se describe los tipos en un ensamblado de common language runtime (CLR).  
  
 Si cualquier parámetro es null, la función devuelve un `HRESULT` de `E_POINTER`. De lo contrario, devuelve `S_OK`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** TlbRef.h  
  
 **Biblioteca:** TlbRef.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones auxiliares Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [LoadTypeLibEx de la función](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
