---
description: 'Más información acerca de: método ImportFile'
title: ImportFile (Método)
ms.date: 03/30/2017
api_name:
- IALink.ImportFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile
helpviewer_keywords:
- ImportFile method
ms.assetid: bcbe321f-b83a-4e9a-9f10-8d913e244dc9
topic_type:
- apiref
ms.openlocfilehash: 82c9c7de7cd739ee205dc3695ea651643d01ea3a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718166"
---
# <a name="importfile-method"></a>ImportFile (Método)

Importa ensamblados y módulos sin enlazar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ImportFile(  
    LPCWSTR pszFilename,  
    LPCWSTR pszTargetName,  
    BOOL fSmartImport,  
    mdToken* pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD* pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  

 `pszFilename`  
 Nombre completo del archivo que se va a importar.  
  
 `pszTargetName`  
 Nombre opcional del archivo de salida que se puede usar para cambiar el nombre del archivo a medida que está vinculado al ensamblado.  
  
 `fSmartImport`  
 Si es TRUE, se usa ImportTypes (; de lo contrario, la importación se debe realizar manualmente.  
  
 `pImportToken`  
 Puntero al token en el que se almacenará un identificador de archivo único. El archivo puede ser un ensamblado o un archivo.  
  
 `ppAssemblyScope`  
 Recibe un puntero a la [interfaz IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md). Puede ser NULL si el archivo no es un ensamblado.  
  
 `pdwCountOfScopes`  
 Puntero al recuento de archivos y/o ámbitos que se han importado.  
  
## <a name="return-value"></a>Valor devuelto  

 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 Requiere ALink. h  
  
## <a name="see-also"></a>Vea también

- [IALink (Interfaz)](ialink-interface.md)
- [IALink2 (Interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
