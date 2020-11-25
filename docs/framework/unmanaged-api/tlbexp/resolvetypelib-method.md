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
ms.openlocfilehash: 84eea78b9c2e73e24238a5ecbc9442f3d63dbd4e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719793"
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
 de [BSTR](/previous-versions/windows/desktop/automat/bstr) que contiene el nombre simple de la biblioteca de tipos.  
  
 `tlbid`  
 de GUID asignado a la biblioteca de tipos en el registro.  
  
 `lcid`  
 de IDENTIFICADOR de localización de la biblioteca de tipos.  
  
 `wMajorVersion`  
 de Número de versión principal de la biblioteca de tipos. Por ejemplo, para la versión *x. y*, el número de versión principal es *x*.  
  
 `wMinorVersion`  
 de Número de versión secundaria de la biblioteca de tipos. Por ejemplo, para la versión *x. y*, el número de versión secundaria es *y*.  
  
 `syskind`  
 de Marca [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) que identifica el entorno operativo. Los valores comunes son SYS_WIN32 y SYS_WIN64.  
  
 `pbstrResolvedTlbName`  
 enuncia Un puntero a un [BSTR](/previous-versions/windows/desktop/automat/bstr) que contiene la ruta de acceso completa de la biblioteca de tipos con el nombre en el `bstrSimpleName` parámetro.  
  
## <a name="remarks"></a>Comentarios  

 `ResolveTypeLib`La [función LoadTypeLibWithResolver (](loadtypelibwithresolver-function.md) llama al método durante el procesamiento de [Tlbexp.exe (exportador de la biblioteca de tipos)](../../tools/tlbexp-exe-type-library-exporter.md) .  
  
 Las implementaciones personalizadas de esta interfaz deben devolver un [BSTR](/previous-versions/windows/desktop/automat/bstr) que contenga la ruta de acceso completa de la biblioteca de tipos denominada en el `bstrSimpleName` parámetro.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** TlbRef. idl, TlbRef. h  
  
 **Biblioteca:** TlbRef. lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Funciones del asistente Tlbexp](index.md)
- [LoadTypeLibEx](/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
