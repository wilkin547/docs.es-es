---
title: ICLRMetaHost::ExitProcess (Método)
ms.date: 03/30/2017
api_name:
- ICLRMetaHost.ExitProcess
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRMetaHost::ExitProcess
helpviewer_keywords:
- ICLRMetaHost::ExitProcess method [.NET Framework hosting]
- ExitProcess method, ICLRMetaHost interface [.NET Framework hosting]
ms.assetid: b4df98cc-4e4e-407b-b8f4-e0076afef3a4
topic_type:
- apiref
ms.openlocfilehash: 6d601ac3ece801353b630c74ed852c2657f25d7f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730469"
---
# <a name="iclrmetahostexitprocess-method"></a>ICLRMetaHost::ExitProcess (Método)

Intenta cerrar todos los tiempos de ejecución cargados correctamente y, a continuación, finaliza el proceso. Reemplaza la función [CorExitProcess (](corexitprocess-function.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a>Parámetros  

 `iExitCode`  
 de Código de salida para el proceso.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método nunca devuelve, por lo que el valor devuelto es indefinido.  
  
## <a name="remarks"></a>Observaciones  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Metahost. h  
  
 **Biblioteca:** Se incluye como un recurso en MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICLRMetaHost (Interfaz)](iclrmetahost-interface.md)
- [Hospedar aplicaciones de WPF](index.md)
