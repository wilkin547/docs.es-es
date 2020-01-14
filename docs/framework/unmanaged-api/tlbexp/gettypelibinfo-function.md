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
ms.openlocfilehash: 4f05eb2e6ef31cf1993a623c38bb177f7e3c297e
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935652"
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
  
## <a name="parameters"></a>Parameters  
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
  
## <a name="remarks"></a>Notas  
 La función `GetTypeLibInfo` se llama mediante el método [Tlbexp. exe (exportador de la biblioteca de tipos)](../../tools/tlbexp-exe-type-library-exporter.md). Esta herramienta genera una biblioteca de tipos que describe los tipos de un ensamblado de Common Language Runtime (CLR).  
  
 Si un parámetro es null, la función devuelve un `HRESULT` de `E_POINTER`. De lo contrario, devuelve `S_OK`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** TlbRef. h  
  
 **Biblioteca:** TlbRef. lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones del asistente Tlbexp](index.md)
- [LoadTypeLibEx función)](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
