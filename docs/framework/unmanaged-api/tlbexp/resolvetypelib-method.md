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
ms.openlocfilehash: be2558e760be8519e528baeff438273c8871f320
ms.sourcegitcommit: 412bbc2e43c3b6ca25b358cdf394be97336f0c24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 08/25/2018
ms.locfileid: "42924474"
---
# <a name="resolvetypelib-method"></a>ResolveTypeLib (Método)
Resuelve el nombre de una biblioteca de tipos simple devolviendo su ruta de acceso completa.  
  
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
 [in] Un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) que contiene el nombre de la biblioteca de tipos simple.  
  
 `tlbid`  
 [in] El GUID asignado a la biblioteca de tipos en el registro.  
  
 `lcid`  
 [in] El identificador de localización de la biblioteca de tipos.  
  
 `wMajorVersion`  
 [in] El número de versión principal de la biblioteca de tipos. Por ejemplo, para la versión *x.y*, el número de versión principal es *x*.  
  
 `wMinorVersion`  
 [in] El número de versión secundaria de la biblioteca de tipos. Por ejemplo, para la versión *x.y*, el número de versión secundaria es *y*.  
  
 `syskind`  
 [in] Un [SYSKIND](https://docs.microsoft.com/previous-versions/windows/desktop/api/oaidl/ne-oaidl-tagsyskind) marca que identifica el entorno operativo. Los valores habituales son SYS_WIN32 y SYS_WIN64.  
  
 `pbstrResolvedTlbName`  
 [out] Un puntero a un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) que contiene la ruta de acceso completa de la biblioteca de tipos con nombre en el `bstrSimpleName` parámetro.  
  
## <a name="remarks"></a>Comentarios  
 El `ResolveTypeLib` llama al método el [LoadTypeLibWithResolver (función)](../../../../docs/framework/unmanaged-api/tlbexp/loadtypelibwithresolver-function.md) durante [Tlbexp.exe (exportador de biblioteca)](../../../../docs/framework/tools/tlbexp-exe-type-library-exporter.md) de procesamiento.  
  
 Las implementaciones personalizadas de esta interfaz deben devolver un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) que contiene la ruta de acceso completa de la biblioteca de tipos con nombre en el `bstrSimpleName` parámetro.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** TlbRef.idl, TlbRef.h  
  
 **Biblioteca:** TlbRef.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones auxiliares Tlbexp](../../../../docs/framework/unmanaged-api/tlbexp/index.md)  
 [LoadTypeLibEx de la](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
