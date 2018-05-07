---
title: ICLRDebuggingLibraryProvider::ProvideLibrary (Método)
ms.date: 03/30/2017
api_name:
- ICLRDebuggingLibraryProvider.ProvideLibrary Method
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICLRDebuggingLibraryProvider::ProvideLibrary
helpviewer_keywords:
- ProvideLibrary method [.NET Framework debugging]
- ICLRDebuggingLibraryProvider::ProvideLibrary method [.NET Framework debugging]
ms.assetid: 86f06245-9517-49be-8d8c-ca5deaf34c02
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: b0644258eb1622f388f55d0657c8922079fe4dc1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a>ICLRDebuggingLibraryProvider::ProvideLibrary (Método)
Obtiene a un proveedor de bibliotecas de interfaz de devolución de llamada que permite a common language runtime (CLR) bibliotecas de depuración específicas de la versión buscar y cargar a petición.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT ProvideLibrary(  
     [in] const WCHAR* pwszFileName,  
     [in] DWORD dwTimestamp,  
     [in] DWORD dwSizeOfImage,  
     [out] HMODULE* hModule);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `pwszFilename`  
 [in] El nombre del módulo que se solicita.  
  
 `dwTimestamp`  
 [in] La marca de tiempo de fecha que se almacena en el encabezado del archivo COFF de archivos PE.  
  
 `pLibraryProvider`  
 [in] El `SizeOfImage` campo almacenado en el encabezado de archivo opcional COFF de archivos PE.  
  
 `hModule`  
 [out] El identificador para el módulo solicitado.  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente.|  
  
## <a name="exceptions"></a>Excepciones  
  
## <a name="remarks"></a>Comentarios  
 `ProvideLibrary` permite al depurador proporcionar módulos que son necesarios para depurar determinados archivos CLR como mscordbi.dll y mscordacwks.dll. Los identificadores de módulo tienen que será válido hasta que una llamada a la [ICLRDebugging:: CanUnloadNow](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) método indica que se pueden liberar, momento en que es responsabilidad del llamador liberar los identificadores.  
  
 El depurador puede usar cualquier medio disponible para buscar u obtener el módulo de depuración.  
  
> [!IMPORTANT]
>  Esta característica permite al llamador de API proporcionar módulos que contienen código ejecutable y posiblemente malintencionado. Como precaución de seguridad, el llamador no debe usar `ProvideLibrary` para distribuir cualquier código que no está dispuesto a ejecutar por sí mismo.  
>   
>  Si se detecta un problema de seguridad grave en una biblioteca ya liberada, como mscordbi.dll o mscordacwks.dll, se puede revisar la corrección de compatibilidad para que reconozca las versiones incorrectas de los archivos. La corrección de compatibilidad puede emitir solicitudes para las versiones de los archivos revisadas y rechazar las versiones incorrectas si se proporcionan en respuesta a cualquier solicitud. Esto puede ocurrir solamente si el usuario ha aplicado revisiones a una nueva versión de la corrección de compatibilidad. Las versiones sin revisar seguirán siendo vulnerables.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)  
 [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
