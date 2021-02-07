---
description: 'Más información sobre: método Importfile2 ('
title: ImportFile2 (Método)
ms.date: 03/30/2017
api_name:
- IALink.ImportFile2
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ImportFile2
helpviewer_keywords:
- ImportFile2 method
ms.assetid: 9a6be861-c260-4a35-acea-3372ea515a0f
topic_type:
- apiref
ms.openlocfilehash: 98da8ecf4bfc19e52c5a92e6509f6af49afbdd5f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99718062"
---
# <a name="importfile2-method"></a>ImportFile2 (Método)

Importa ensamblados y módulos sin enlazar. Este método es como el [método importFile](importfile-method.md), pero funciona incluso si el archivo que se va a importar no existe en el disco.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ImportFile2(  
    LPCWSTR         pszFilename,  
    LPCWSTR         pszTargetName,  
    IMetaDataAssemblyImport* pAssemblyScopeIn,  
    BOOL            fSmartImport,  
    mdToken*        pImportToken,  
    IMetaDataAssemblyImport** ppAssemblyScope,  
    DWORD*          pdwCountOfScopes  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  

 `pszFilename`  
 Nombre del archivo que se va a importar.  
  
 `pszTargetName`  
 Nombre opcional del archivo de salida que se puede usar para cambiar el nombre del archivo a medida que está vinculado al ensamblado.  
  
 `pAssemblyScopeIn`  
 Interfaz de [interfaz IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) de ámbito opcional.  
  
 `fSmartImport`  
 Si es TRUE, se usa ImportTypes (; de lo contrario, la importación se debe realizar manualmente.  
  
 `pImportToken`  
 Recibe el identificador del archivo o ensamblado.  
  
 `ppAssemblyScope`  
 Recibe la interfaz de la [interfaz IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) . Es NULL si el archivo no es un ensamblado.  
  
 `pdwCountOfScopes`  
 Recibe el encontrado de archivos y/o ámbitos importados.  
  
## <a name="return-value"></a>Valor devuelto  

 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 Requiere ALink. h.  
  
## <a name="see-also"></a>Vea también

- [IALink (Interfaz)](ialink-interface.md)
- [IALink2 (Interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
