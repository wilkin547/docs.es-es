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
ms.openlocfilehash: e64a0512e05965b3da2e7486e986ee34ca8a20d6
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73104301"
---
# <a name="gettypelibinfo-function"></a>GetTypeLibInfo (Función)
Devuelve información sobre la biblioteca de tipos especificada examinando su estructura [TLIBATTR](https://docs.microsoft.com/windows/win32/api/oaidl/ns-oaidl-tlibattr) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
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
 de Nombre de archivo de la biblioteca de tipos.  
  
 `pTypeLibID`  
 enuncia GUID de la biblioteca de tipos.  
  
 `pTypeLibLCID`  
 enuncia IDENTIFICADOR de localización de la biblioteca de tipos.  
  
 `pTypeLibPlatform`  
 enuncia Marca [SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) que identifica el sistema operativo de destino de la biblioteca de tipos. Los valores comunes son SYS_WIN32 y SYS_WIN64.  
  
 `pTypeLibMajorVer`  
 enuncia Número de versión principal de la biblioteca de tipos. Por ejemplo, para la versión *x. y*, el número de versión principal es *x*.  
  
 `pTypeLibMinorVer`  
 enuncia Número de versión secundaria de la biblioteca de tipos. Por ejemplo, para la versión *x. y*, el número de versión secundaria es *y*.  
  
## <a name="remarks"></a>Comentarios  
 La función `GetTypeLibInfo` se llama mediante el método [Tlbexp. exe (exportador de la biblioteca de tipos)](../../tools/tlbexp-exe-type-library-exporter.md). Esta herramienta genera una biblioteca de tipos que describe los tipos de un ensamblado de Common Language Runtime (CLR).  
  
 Si un parámetro es null, la función devuelve un `HRESULT` de `E_POINTER`. De lo contrario, devuelve `S_OK`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** TlbRef. h  
  
 **Biblioteca:** TlbRef. lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones del asistente Tlbexp](index.md)
- [LoadTypeLibEx función)](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
