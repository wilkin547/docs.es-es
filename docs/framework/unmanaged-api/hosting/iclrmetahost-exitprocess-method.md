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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: fc71762fb4a660cf84814cdd46d09696a161f3c9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33431602"
---
# <a name="iclrmetahostexitprocess-method"></a>ICLRMetaHost::ExitProcess (Método)
Intenta cerrar todos los runtime cargados correctamente y, a continuación, finaliza el proceso. Reemplaza el [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `iExitCode`  
 [in] El código de salida para el proceso.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método nunca devuelve, por lo que su valor devuelto es indefinido.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MetaHost.h  
  
 **Biblioteca:** incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [ICLRMetaHost (interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)  
 [Hospedar aplicaciones de WPF](../../../../docs/framework/unmanaged-api/hosting/index.md)
