---
title: ICorDebugMetaDataLocator::GetMetaData (Método)
ms.date: 03/30/2017
api_name:
- ICorDebugMetaDataLocator.GetMetaData
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugMetaDataLocator::GetMetaData
helpviewer_keywords:
- ICorDebugMetaDataLocator::GetMetaData method [.NET Framework debugging]
- GetMetaData method, ICorDebugMetaDataLocator interface [.NET Framework debugging]
ms.assetid: f9b0ff22-54db-45eb-9cc3-508000a3141d
topic_type:
- apiref
ms.openlocfilehash: 63efb788d8bca84da94921371309704cc7b20ac4
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95710446"
---
# <a name="icordebugmetadatalocatorgetmetadata-method"></a>ICorDebugMetaDataLocator::GetMetaData (Método)

Pide al depurador que devuelva la ruta de acceso completa a un módulo cuyos metadatos se necesitan para completar una operación solicitada por el depurador.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetMetaData(  
      [in] LPCWSTR wszImagePath,  
      [in] DWORD   dwImageTimeStamp,  
      [in] DWORD   dwImageSize,  
      [in] ULONG32 cchPathBuffer,  
      [out] ULONG32 * pcchPathBuffer,  
      [out, size_is(cchPathBuffer), length_is(*pcchPathBuffer)]  
               WCHAR wszPathBuffer[]  
      );  
```  
  
## <a name="parameters"></a>Parámetros  

 `wszImagePath`  
 [in] Cadena terminada en NULL que representa la ruta de acceso completa al archivo. Si la ruta de acceso completa no está disponible, el nombre y la extensión del archivo (*filename*.*extensión*).  
  
 `dwImageTimeStamp`  
 [in] Marca de tiempo de los encabezados del archivo PE de la imagen. Este parámetro puede usarse potencialmente para una búsqueda del servidor de símbolos ([SymSrv](/windows/desktop/debug/using-symsrv)).  
  
 `dwImageSize`  
 [in] Tamaño de la imagen en los encabezados de archivo PE. Este parámetro podría usarse para una búsqueda de SymSrv.  
  
 `cchPathBuffer`  
 [in] Número de caracteres de `wszPathBuffer`.  
  
 `pcchPathBuffer`  
 [out] Número de `WCHAR` escritos en `wszPathBuffer`.  
  
 Si el método devuelve E_NOT_SUFFICIENT_BUFFER, contiene el número de `WCHAR` necesarios para almacenar la ruta de acceso.  
  
 `wszPathBuffer`  
 [out] Puntero a un búfer en el que el depurador copiará la ruta de acceso completa del archivo que contiene los metadatos solicitados.  
  
 La `ofReadOnly` marca de la enumeración [CorOpenFlags (](../metadata/coropenflags-enumeration.md) se usa para solicitar acceso de solo lectura a los metadatos de este archivo.  
  
## <a name="return-value"></a>Valor devuelto  

 Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método. Cualquier otro HRESULT de error indica que el archivo no se puede recuperar.  
  
|HRESULT|Descripción|  
|-------------|-----------------|  
|S_OK|El método se completó correctamente. `wszPathBuffer` contiene la ruta de acceso completa al archivo y termina en NULL.|  
|E_NOT_SUFFICIENT_BUFFER|El tamaño actual de `wszPathBuffer` no es suficiente para contener la ruta de acceso completa. En este caso, `pcchPathBuffer` contiene el número necesario de `WCHAR`, incluido el carácter NULL final, y se llama a `GetMetaData` una segunda vez con el tamaño de búfer solicitado.|  
  
## <a name="remarks"></a>Comentarios  

 Si `wszImagePath` contiene una ruta de acceso completa para un módulo de un volcado de memoria, especifica la ruta de acceso del equipo desde el que se recopiló el volcado de memoria. Puede que el archivo no exista en esta ubicación o que en ella haya almacenado un archivo incorrecto con el mismo nombre.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugThread4 (Interfaz)](icordebugthread4-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
- [Depuración](index.md)
