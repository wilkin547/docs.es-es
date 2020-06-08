---
title: CLRCreateInstance (Función)
ms.date: 03/30/2017
api_name:
- CLRCreateInstance
api_location:
- mscoree.dll
- mscoreei.dll
api_type:
- COM
f1_keywords:
- CLRCreateInstance
helpviewer_keywords:
- CLRCreateInstance function [.NET Framework hosting]
ms.assetid: 5de13327-96c6-4697-a89e-b8bf40717855
topic_type:
- apiref
ms.openlocfilehash: 4aeacc718632c133550ed8de6649716c5d8b7423
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/08/2020
ms.locfileid: "84504464"
---
# <a name="clrcreateinstance-function"></a>CLRCreateInstance (Función)
Proporciona una de las tres interfaces: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md)o [ICLRDebugging](../debugging/iclrdebugging-interface.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CLRCreateInstance(  
    [in]  REFCLSID  clsid,  
    [in]  REFIID     riid,  
    [out] LPVOID  * ppInterface  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `clsid`  
 de Uno de los tres identificadores de clase: CLSID_CLRMetaHost, CLSID_CLRMetaHostPolicy o CLSID_CLRDebugging.  
  
 `riid`  
 de Uno de los tres identificadores de interfaz (IID): IID_ICLRMetaHost, IID_ICLRMetaHostPolicy o IID_ICLRDebugging.  
  
 `ppInterface`  
 enuncia Una de las tres interfaces: [ICLRMetaHost](iclrmetahost-interface.md), [ICLRMetaHostPolicy](iclrmetahostpolicy-interface.md)o [ICLRDebugging](../debugging/iclrdebugging-interface.md).  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
|E_POINTER|`ppInterface` es null.|  
  
## <a name="remarks"></a>Comentarios  
 En la tabla siguiente se muestran las combinaciones admitidas para `clsid` y `riid` .  
  
|`clsid`|`riid`|  
|--------------|------------|  
|CLSID_CLRMetaHost|IID_ICLRMetaHost|  
|CLSID_CLRMetaHostPolicy|IID_ICLRMetaHostPolicy|  
|CLSID_CLRDebugging|IID_ICLRDebugging|  
  
 En el código siguiente se muestra cómo usar `CLRCreateInstance` para obtener las tres interfaces:  
  
```cpp  
#include <metahost.h>  
#pragma comment(lib, "mscoree.lib")  
  
ICLRMetaHost       *pMetaHost       = NULL;  
ICLRMetaHostPolicy *pMetaHostPolicy = NULL;  
ICLRDebugging      *pCLRDebugging   = NULL;  
HRESULT hr;  
hr = CLRCreateInstance(CLSID_CLRMetaHost, IID_ICLRMetaHost,  
                    (LPVOID*)&pMetaHost);  
hr = CLRCreateInstance (CLSID_CLRMetaHostPolicy, IID_ICLRMetaHostPolicy,  
                    (LPVOID*)&pMetaHostPolicy);  
hr = CLRCreateInstance (CLSID_CLRDebugging, IID_ICLRDebugging,  
                    (LPVOID*)&pCLRDebugging);  
```  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como recurso en MSCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también:

- [Hospedar aplicaciones de WPF](index.md)
