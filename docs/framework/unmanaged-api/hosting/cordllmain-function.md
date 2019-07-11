---
title: _CorDllMain (Función)
ms.date: 03/30/2017
api_name:
- _CorDllMain
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- _CorDllMain
helpviewer_keywords:
- _CorDllMain function [.NET Framework hosting]
ms.assetid: bc7b51cf-39d3-48ec-a5cb-2f179fbefff8
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 9a02a899fd6fbffd04ef25913adb6a65ade27177
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67755660"
---
# <a name="cordllmain-function"></a>\_Función CorDllMain

Inicializa common language runtime (CLR), busca el punto de entrada administrado en el encabezado CLR del ensamblado DLL y comienza la ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `hInst`  
 [in] El identificador de instancia del módulo cargado.  
  
 `dwReason`  
 [in] Indica por qué se llama a la función de punto de entrada DLL. Este parámetro puede ser uno de los siguientes valores: DLL\_PROCESS_ATTACH, DLL\_subprocesos\_ATTACH, DLL\_subprocesos\_adjuntar o DLL\_proceso\_DETACH. Para obtener descripciones de estos valores, vea el `DllMain` documentación de Platform SDK.  
  
 `lpReserved`  
 [in] Sin usar.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve `true` para el éxito y `false` si se produce un error.  
  
## <a name="remarks"></a>Comentarios  
 El cargador del sistema operativo llama a esta función para los ensamblados DLL. Para los ensamblados ejecutables, el cargador llama a la [ \_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) funcione en su lugar.  
  
 El cargador del sistema operativo llama a este método independientemente del punto de entrada especificado en el archivo DLL.  
  
El `_CorDllMain` función se llama directamente mediante el cargador del sistema operativo.
  
 Para obtener más información, vea la sección de comentarios en el [ \_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) tema.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
