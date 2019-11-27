---
title: ISymUnmanagedBinder3::GetReaderFromCallback (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder3.GetReaderFromCallback
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder3::GetReaderFromCallback
helpviewer_keywords:
- GetReaderFromCallback method [.NET Framework debugging]
- ISymUnmanagedBinder3::GetReaderFromCallback method [.NET Framework debugging]
ms.assetid: 4ef83bd2-3d8e-499e-8a12-d9d6fd6ced30
topic_type:
- apiref
ms.openlocfilehash: a0cccc0adfc666cc8e373bc1f89c8f6f97068fde
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449302"
---
# <a name="isymunmanagedbinder3getreaderfromcallback-method"></a>ISymUnmanagedBinder3::GetReaderFromCallback (Método)
Permite al usuario implementar o proporcionar a través de una devolución de llamada, o bien un `IID_IDiaReadExeAtRVACallback` o `IID_IDiaReadExeAtOffsetCallback` para obtener la información del directorio de depuración de la memoria.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetReaderFromCallback(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
    [in]  IUnknown     *callback,  
    [out,retval] ISymUnmanagedReader  **pRetVal);  
```  
  
## <a name="parameters"></a>Parámetros  
 `importer`  
 de Puntero a la interfaz de importación de metadatos.  
  
 `fileName`  
 de Puntero al nombre de archivo.  
  
 `searchPath`  
 de Puntero a la ruta de acceso de búsqueda.  
  
 `searchPolicy`  
 de Un valor de la enumeración [corsymsearchpolicyattributes (](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md) que especifica la Directiva que se va a usar al realizar una búsqueda de un lector de símbolos.  
  
 `callback`  
 de Puntero a la función de devolución de llamada.  
  
 `pRetVal`  
 enuncia Puntero que se establece en la interfaz [ISymUnmanagedReader](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-interface.md) devuelta.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedBinder3 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder3-interface.md)
