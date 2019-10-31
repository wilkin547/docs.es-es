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
ms.openlocfilehash: 8fc2abd0728115edbbfae42958d8013029523ed1
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73111359"
---
# <a name="iclrdebugginglibraryproviderprovidelibrary-method"></a>ICLRDebuggingLibraryProvider::ProvideLibrary (Método)

Obtiene una interfaz de devolución de llamada del proveedor de bibliotecas que permite localizar y cargar a petición bibliotecas de depuración específicas de la versión de Common Language Runtime (CLR).

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT ProvideLibrary(
     [in] const WCHAR* pwszFileName,
     [in] DWORD dwTimestamp,
     [in] DWORD dwSizeOfImage,
     [out] HMODULE* hModule);
```

## <a name="parameters"></a>Parámetros

`pwszFilename` \
de Nombre del módulo que se está solicitando.

`dwTimestamp` \
de Marca de fecha y hora almacenada en el encabezado de archivo COFF de archivos PE.

`pLibraryProvider` \
de El campo `SizeOfImage` almacenado en el encabezado de archivo COFF opcional de los archivos PE.

`hModule` \
enuncia Identificador del módulo solicitado.

## <a name="return-value"></a>Valor devuelto

Este método devuelve los siguientes HRESULT específicos y los errores HRESULT que indican un error del método.

|HRESULT|Descripción|
|-------------|-----------------|
|S_OK|El método se completó correctamente.|

## <a name="exceptions"></a>Excepciones

## <a name="remarks"></a>Comentarios

`ProvideLibrary` permite al depurador proporcionar los módulos necesarios para depurar archivos CLR específicos como mscordbi. dll y mscordacwks. dll. Los identificadores de módulo deben seguir siendo válidos hasta que una llamada al método [ICLRDebugging:: canunloadnow (](../../../../docs/framework/unmanaged-api/debugging/iclrdebugging-canunloadnow-method.md) indica que se pueden liberar, momento en el que es responsabilidad del llamador liberar los identificadores.

El depurador puede utilizar cualquier medio disponible para buscar o adquirir el módulo de depuración.

> [!IMPORTANT]
> Esta característica permite al llamador de la API proporcionar módulos que contienen código ejecutable y posiblemente malintencionado. Como medida de seguridad, el autor de la llamada no debe utilizar `ProvideLibrary` para distribuir ningún código que no esté dispuesto a ejecutarse a sí mismo.
>
> Si se detecta un problema de seguridad grave en una biblioteca ya publicada, como mscordbi. dll o mscordacwks. dll, se pueden aplicar revisiones a las correcciones de compatibilidad para reconocer las versiones incorrectas de los archivos. A continuación, la corrección de compatibilidad puede emitir solicitudes para las versiones revisadas de los archivos y rechazar las versiones incorrectas Si se proporcionan como respuesta a cualquier solicitud. Esto solo puede ocurrir si el usuario ha revisado una nueva versión de la corrección de compatibilidad (shim). Las versiones sin revisar seguirán siendo vulnerables.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado:** CorDebug.idl, CorDebug.h

**Biblioteca:** CorGuids.lib

**Versiones de .NET Framework:** [!INCLUDE[net_current_v40plus](../../../../includes/net-current-v40plus-md.md)]

## <a name="see-also"></a>Vea también

- [Interfaces de depuración](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)
- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
