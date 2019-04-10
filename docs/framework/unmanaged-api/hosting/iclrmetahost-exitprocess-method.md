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
ms.openlocfilehash: 64c212d064ad658678926690d1e680afe27c7c99
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59219244"
---
# <a name="iclrmetahostexitprocess-method"></a>ICLRMetaHost::ExitProcess (Método)
Intenta cerrar todos los runtime cargados correctamente y, a continuación, finaliza el proceso. Reemplaza el [CorExitProcess](../../../../docs/framework/unmanaged-api/hosting/corexitprocess-function.md) función.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ExitProcess (  
    [in] INT32 iExitCode);  
```  
  
## <a name="parameters"></a>Parámetros  
 `iExitCode`  
 [in] El código de salida para el proceso.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método nunca devuelve, por lo que su valor devuelto es indefinido.  
  
## <a name="remarks"></a>Comentarios  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: MetaHost.h  
  
 **Biblioteca:** Incluye como recurso en MSCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [ICLRMetaHost (Interfaz)](../../../../docs/framework/unmanaged-api/hosting/iclrmetahost-interface.md)
- [Hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md)
