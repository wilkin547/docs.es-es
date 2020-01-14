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
ms.openlocfilehash: f0f6fe321f4d38129b6d70ce94a7ea8de8fff6c8
ms.sourcegitcommit: 7e2128d4a4c45b4274bea3b8e5760d4694569ca1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/14/2020
ms.locfileid: "75935668"
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
  
## <a name="parameters"></a>Parameters  
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
 de Marca [SYSKIND](/windows/win32/api/oaidl/ne-oaidl-syskind) que identifica el entorno operativo. Los valores comunes son SYS_WIN32 y SYS_WIN64.  
  
 `pbstrResolvedTlbName`  
 enuncia Un puntero a un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) que contiene la ruta de acceso completa de la biblioteca de tipos denominada en el parámetro `bstrSimpleName`.  
  
## <a name="remarks"></a>Notas  
 La [función LoadTypeLibWithResolver (](loadtypelibwithresolver-function.md) llama al método `ResolveTypeLib` durante el procesamiento de [Tlbexp. exe (exportador de la biblioteca de tipos)](../../tools/tlbexp-exe-type-library-exporter.md) .  
  
 Las implementaciones personalizadas de esta interfaz deben devolver un [BSTR](https://docs.microsoft.com/previous-versions/windows/desktop/automat/bstr) que contenga la ruta de acceso completa de la biblioteca de tipos denominada en el parámetro `bstrSimpleName`.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** TlbRef. idl, TlbRef. h  
  
 **Biblioteca:** TlbRef. lib  
  
 **.NET Framework versiones:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones del asistente Tlbexp](index.md)
- [LoadTypeLibEx](https://docs.microsoft.com/previous-versions/windows/desktop/api/oleauto/nf-oleauto-loadtypelibex)
