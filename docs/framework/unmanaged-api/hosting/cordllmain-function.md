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
ms.openlocfilehash: a5d541f834e829305fa2b091c45d0dc8f387bb55
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="cordllmain-function"></a>_CorDllMain (Función)
Inicializa common language runtime (CLR), busca el punto de entrada administrado en el encabezado CLR del ensamblado de la DLL y comienza la ejecución.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
BOOL STDMETHODCALLTYPE _CorDllMain (  
   [in] HINSTANCE hInst,  
   [in] DWORD     dwReason,  
   [in] LPVOID    lpReserved  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `hInst`  
 [in] El identificador de instancia del módulo cargado.  
  
 `dwReason`  
 [in] Indica por qué se llama a la función de punto de entrada DLL. Este parámetro puede ser uno de los valores siguientes: DLL_PROCESS_ATTACH, DLL_THREAD_ATTACH, DLL_THREAD_ATTACH o DLL_PROCESS_DETACH. Para obtener descripciones de estos valores, consulte el `DllMain` documentación de Platform SDK.  
  
 `lpReserved`  
 [in] No se utiliza.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve `true` para el éxito y `false` si se produce un error.  
  
## <a name="remarks"></a>Comentarios  
 El cargador del sistema operativo llama a esta función para los ensamblados DLL. Para los ensamblados ejecutables, el cargador llama a la [_CorExeMain](../../../../docs/framework/unmanaged-api/hosting/corexemain-function.md) funcione en su lugar.  
  
 El cargador del sistema operativo llama a este método sin tener en cuenta el punto de entrada especificado en el archivo DLL.  
  
 En Windows 98, Windows ME, Windows NT y Windows 2000, la `_CorDllMain` función se llama indirectamente a través de un fixupin el cargador del sistema operativo. En las demás versiones de Windows, se llama directamente por el cargador del sistema operativo.  
  
 Para obtener más información, vea la sección comentarios en el [_CorValidateImage](../../../../docs/framework/unmanaged-api/hosting/corvalidateimage-function.md) tema.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Funciones estáticas globales para metadatos](../../../../docs/framework/unmanaged-api/metadata/metadata-global-static-functions.md)
