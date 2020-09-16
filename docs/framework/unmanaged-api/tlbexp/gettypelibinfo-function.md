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
ms.openlocfilehash: 4c630f5f7e3dc66ce44f10cd69fcd108226b0250
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90554337"
---
# <a name="gettypelibinfo-function"></a>GetTypeLibInfo (Función)
Devuelve información sobre la biblioteca de tipos especificada examinando su estructura [TLIBATTR](/windows/win32/api/oaidl/ns-oaidl-tlibattr) .  
  
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
 enuncia Marca [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) que identifica el sistema operativo de destino de la biblioteca de tipos. Los valores comunes son SYS_WIN32 y SYS_WIN64.  
  
 `pTypeLibMajorVer`  
 enuncia Número de versión principal de la biblioteca de tipos. Por ejemplo, para la versión *x. y*, el número de versión principal es *x*.  
  
 `pTypeLibMinorVer`  
 enuncia Número de versión secundaria de la biblioteca de tipos. Por ejemplo, para la versión *x. y*, el número de versión secundaria es *y*.  
  
## <a name="remarks"></a>Comentarios  
 El `GetTypeLibInfo` [Tlbexp.exe (exportador de la biblioteca de tipos)](../../tools/tlbexp-exe-type-library-exporter.md)llama a la función. Esta herramienta genera una biblioteca de tipos que describe los tipos de un ensamblado de Common Language Runtime (CLR).  
  
 Si un parámetro es null, la función devuelve un `HRESULT` de `E_POINTER` . En caso contrario, devuelve `S_OK`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** TlbRef. h  
  
 **Biblioteca:** TlbRef. lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones del asistente Tlbexp](index.md)
- [LoadTypeLibEx función)](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
