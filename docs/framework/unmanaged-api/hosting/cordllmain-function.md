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
ms.openlocfilehash: f60f159ab4770023cee7123b39109040243e1ccd
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73136974"
---
# <a name="_cordllmain-function"></a>\_función CorDllMain

Inicializa el Common Language Runtime (CLR), busca el punto de entrada administrado en el encabezado CLR del ensamblado de DLL y comienza la ejecución.  
  
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
 de Identificador de instancia del módulo cargado.  
  
 `dwReason`  
 de Indica por qué se llama a la función de punto de entrada del archivo DLL. Este parámetro puede ser uno de los siguientes valores: DLL\_PROCESS_ATTACH, DLL\_subproceso\_adjuntar, DLL\_subproceso\_adjuntar o DLL\_procesar\_desasociar. Para obtener descripciones de estos valores, consulte la documentación de `DllMain` en el SDK de la plataforma.  
  
 `lpReserved`  
 de Sin usar.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve `true` para Success y `false` si se produce un error.  
  
## <a name="remarks"></a>Comentarios  
 El cargador del sistema operativo llama a esta función para los ensamblados DLL. En el caso de los ensamblados ejecutables, el cargador llama a la función [\_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) en su lugar.  
  
 El cargador del sistema operativo llama a este método independientemente del punto de entrada especificado en el archivo DLL.  
  
El cargador del sistema operativo llama directamente a la función `_CorDllMain`.
  
 Para obtener más información, vea la sección Comentarios del tema [\_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) .  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones estáticas globales para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
