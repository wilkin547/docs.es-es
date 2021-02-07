---
description: 'Más información sobre: Isymunmanagedbinder2 (:: Getreaderforfile2 ((método)'
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
ms.openlocfilehash: c1a180ceec07c3087150613365acfce646adc34e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99689942"
---
# <a name="isymunmanagedbinder2getreaderforfile2-method"></a>ISymUnmanagedBinder2::GetReaderForFile2 (Método)

Dada una interfaz de metadatos y un nombre de archivo, devuelve la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) correcta que leerá los símbolos de depuración asociados al módulo.  
  
 Este método proporciona una búsqueda más extensa del archivo de base de datos de programa (PDB) que el método [ISymUnmanagedBinder:: GetReaderForFile (](isymunmanagedbinder-getreaderforfile-method.md) .  
  
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
 de Un valor de la enumeración [corsymsearchpolicyattributes (](corsymsearchpolicyattributes-enumeration.md) que especifica la Directiva que se va a usar al realizar una búsqueda de un lector de símbolos.  
  
 `pRetVal`  
 enuncia Puntero que se establece en la interfaz [ISymUnmanagedReader](isymunmanagedreader-interface.md) devuelta.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="remarks"></a>Observaciones  

 Esta versión del método puede buscar el archivo PDB en áreas distintas de la derecha junto al módulo. La Directiva de búsqueda se puede controlar mediante la combinación de [corsymsearchpolicyattributes (](corsymsearchpolicyattributes-enumeration.md). Por ejemplo, `AllowReferencePathAccess | AllowSymbolServerAccess` busca el archivo PDB junto al archivo ejecutable y en un servidor de símbolos, pero no consulta el registro o usa la ruta de acceso en el archivo ejecutable. Si `searchPath` se proporciona el parámetro, se buscará siempre esos directorios.  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedBinder2 (Interfaz)](isymunmanagedbinder2-interface.md)
- [Método GetReaderForFile](isymunmanagedbinder-getreaderforfile-method.md)
