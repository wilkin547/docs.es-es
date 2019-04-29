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
ms.openlocfilehash: d12cbb66464baba4ee706ccb076764fbf025fc5f
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61786183"
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
  
## <a name="parameters"></a>Parámetros  
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
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: TlbRef.h  
  
 **Biblioteca:** TlbRef.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones del asistente Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [LoadTypeLibEx de la función](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
