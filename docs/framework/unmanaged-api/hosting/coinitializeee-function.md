---
title: CoInitializeEE (Función)
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ca85a12191db51818da2a08910dc9524d1ac9498
ms.sourcegitcommit: 79066169e93d9d65203028b21983574ad9dcf6b4
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/01/2019
ms.locfileid: "57211824"
---
# <a name="coinitializeee-function"></a>CoInitializeEE (Función)
Garantiza que el motor de ejecución de common language runtime se carga en un proceso. Esta función está en desuso en el [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]. Use la [ICLRRuntimeHost:: Start](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-start-method.md) método en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `fFlags`  
 [in] Uno de los [COINITIEE](../../../../docs/framework/unmanaged-api/metadata/coinitiee-enumeration.md) constantes de enumeración.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve códigos de error COM estándar, tal como se define en Winerror.h y los valores en la tabla siguiente.  
  
|Código devuelto|Descripción|  
|-----------------|-----------------|  
|S_OK|El motor de ejecución se cargó correctamente.|  
|S_FALSE|El motor de ejecución ya está cargado.|  
|E_FAIL|No se pudo cargar el motor de ejecución.|  
  
## <a name="remarks"></a>Comentarios  
 Este método carga el motor de ejecución si no se ha cargado anteriormente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también
- [Funciones estáticas globales para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
