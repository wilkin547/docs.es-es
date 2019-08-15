---
title: ResolveTypeLib (Método)
ms.date: 03/30/2017
api_name:
- ResolveTypeLib
api_location:
- tlbref.dll
f1_keywords:
- ResolveTypeLib
helpviewer_keywords:
- ITypeLibResolver::ResolveTypeLib method [.NET Framework]
- ResolveTypeLib method [.NET Framework]
ms.assetid: 95d2aa0d-8eeb-4a9f-a216-5249f7e2c167
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0f274befe78e45be3e53335572fd9c1e0b401fd3
ms.sourcegitcommit: cf9515122fce716bcfb6618ba366e39b5a2eb81e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/15/2019
ms.locfileid: "69040173"
---
# <a name="resolvetypelib-method"></a>ResolveTypeLib (Método)
Resuelve el nombre simple de una biblioteca de tipos devolviendo su ruta de acceso completa.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ResolveTypeLib(  
    [in]  BSTR      bstrSimpleName,  
    [in]  GUID      tlbid,  
    [in]  LCID      lcid,  
    [in]  USHORT    wMajorVersion,  
    [in]  USHORT    wMinorVersion,  
    [in]  SYSKIND   syskind,  
    [out] BSTR     *pbstrResolvedTlbName);  
```  
  
## <a name="parameters"></a>Parámetros  
 `bstrSimpleName`  
 de [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) que contiene el nombre simple de la biblioteca de tipos.  
  
 `tlbid`  
 de GUID asignado a la biblioteca de tipos en el registro.  
  
 `lcid`  
 de IDENTIFICADOR de localización de la biblioteca de tipos.  
  
 `wMajorVersion`  
 de Número de versión principal de la biblioteca de tipos. Por ejemplo, para la versión *x. y*, el número de versión principal es *x*.  
  
 `wMinorVersion`  
 de Número de versión secundaria de la biblioteca de tipos. Por ejemplo, para la versión *x. y*, el número de versión secundaria es *y*.  
  
 `syskind`  
 de Marca [SYSKIND](https://docs.microsoft.com/windows/win32/api/oaidl/ne-oaidl-syskind) que identifica el entorno operativo. Los valores comunes son SYS_WIN32 y SYS_WIN64.  
  
 `pbstrResolvedTlbName`  
 enuncia Un puntero a un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) que contiene la ruta de acceso completa de la biblioteca de tipos `bstrSimpleName` con el nombre en el parámetro.  
  
## <a name="remarks"></a>Comentarios  
 La `ResolveTypeLib` [función LoadTypeLibWithResolver (](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) llama al método durante el procesamiento de [Tlbexp. exe (exportador de la biblioteca de tipos)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) .  
  
 Las implementaciones personalizadas de esta interfaz deben devolver un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) que contenga la ruta de acceso completa de la biblioteca `bstrSimpleName` de tipos denominada en el parámetro.  
  
## <a name="requirements"></a>Requisitos  
 **Select** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: TlbRef. idl, TlbRef. h  
  
 **Biblioteca** TlbRef.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones del asistente Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)
- [LoadTypeLibEx](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
