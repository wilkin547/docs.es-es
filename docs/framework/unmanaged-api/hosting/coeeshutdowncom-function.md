---
title: CoEEShutDownCOM (Función)
ms.date: 03/30/2017
api_name:
- CoEEShutDownCOM
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoEEShutDownCOM
helpviewer_keywords:
- CoEEShutDownCOM function [.NET Framework hosting]
ms.assetid: b634cae2-632f-4737-9be4-92d0652844d7
topic_type:
- apiref
ms.openlocfilehash: 4e85a9a98bf0550fa906f8b905c73890948f4ac1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124939"
---
# <a name="coeeshutdowncom-function"></a>CoEEShutDownCOM (Función)
Obliga al Common Language Runtime (CLR) a liberar todos los punteros de interfaz que contiene dentro de contenedores RCW (Runtime Callable wrappers). Esto tiene el efecto de liberar todas las memorias caché de RCW. Esta función global está en desuso en el .NET Framework 4. En su lugar, use el punto de entrada para un tiempo de ejecución específico.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
void CoEEShutDownCOM ();  
```  
  
## <a name="remarks"></a>Comentarios  
 En primer lugar, la función `CoEEShutDownCOM` libera todos los RCW en todos los contextos y en todas las cachés y, a continuación, quita cualquier notificación de desactivación existente en el programa de instalación. No se produce ninguna descarga del archivo DLL.  
  
> [!CAUTION]
> Esta función afecta a todos los Runtimes que se cargan en el proceso.  
  
 A partir de la .NET Framework 4, llame al punto de entrada de esta función en el tiempo de ejecución específico que desee modificar. Para obtener el punto de entrada, llame al método [ICLRRuntimeInfo:: GetProcAddress](../../../../docs/framework/unmanaged-api/hosting/iclrruntimeinfo-getprocaddress-method.md) y especifique "coeeshutdowncom (".  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
