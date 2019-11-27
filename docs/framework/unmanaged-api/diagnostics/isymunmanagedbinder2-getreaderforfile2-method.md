---
title: ISymUnmanagedBinder2::GetReaderForFile2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedBinder2.GetReaderForFile2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2
helpviewer_keywords:
- ISymUnmanagedBinder2::GetReaderForFile2 method [.NET Framework debugging]
- GetReaderForFile2 method [.NET Framework debugging]
ms.assetid: dd92dcaf-403c-464d-a254-21594985dddd
topic_type:
- apiref
ms.openlocfilehash: 756ba2e71ca2e3e817a0a8b89165bb807368c1f9
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74449335"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a>ISymUnmanagedBinder2::GetReaderForFile2 (Método)
Dada una interfaz de metadatos y un nombre de archivo, devuelve la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) correcta que leerá los símbolos de depuración asociados al módulo.  
  
 Este método proporciona una búsqueda más extensa del archivo de base de datos de programa (PDB) que el método [ISymUnmanagedBinder:: GetReaderForFile (](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetReaderForFile2(  
    [in]  IUnknown     *importer,  
    [in]  const WCHAR  *fileName,  
    [in]  const WCHAR  *searchPath,  
    [in]  ULONG32      searchPolicy,  
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
  
 `pRetVal`  
 enuncia Puntero que se establece en la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) devuelta.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="remarks"></a>Comentarios  
 Esta versión del método puede buscar el archivo PDB en áreas distintas de la derecha junto al módulo. La Directiva de búsqueda se puede controlar mediante la combinación de [corsymsearchpolicyattributes (](../../../../docs/framework/unmanaged-api/diagnostics/corsymsearchpolicyattributes-enumeration.md). Por ejemplo, `AllowReferencePathAccess | AllowSymbolServerAccess` busca el archivo PDB junto al archivo ejecutable y en un servidor de símbolos, pero no consulta el registro o usa la ruta de acceso en el archivo ejecutable. Si se proporciona el parámetro `searchPath`, se buscarán siempre esos directorios.  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedBinder2 (interfaz)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder2-interface.md)
- [GetReaderForFile (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedbinder-getreaderforfile-method.md)
