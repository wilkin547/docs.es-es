---
description: 'Más información sobre: método Setassemblyfile ('
title: SetAssemblyFile (Método)
ms.date: 03/30/2017
api_name:
- IALink.SetAssemblyFile
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetAssemblyFile
helpviewer_keywords:
- SetAssemblyFile method
ms.assetid: 3a912787-f139-43ca-a841-8bbda3107ecf
topic_type:
- apiref
ms.openlocfilehash: 943e0600b9781aeaf45cc26e39bd8a8b33a783c2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662499"
---
# <a name="setassemblyfile-method"></a>SetAssemblyFile (Método)

Asigna el nombre del ensamblado que se va a compilar. No se usa al generar módulos no enlazados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetAssemblyFile(  
    LPCWSTR pszFilename,  
    IMetaDataEmit* pEmitter,  
    AssemblyFlags afFlags,  
    mdAssembly* pAssemblyID  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  

 `pszFilename`  
 Nombre completo del archivo de manifiesto.  
  
 `pEmitter`  
 Puntero a la interfaz de [interfaz IMetaDataEmit](../metadata/imetadataemit-interface.md) .  
  
 `afFlags`  
 Marcas tal y como se definen en la [enumeración AssemblyFlags (](../metadata/assemblyflags-enumeration.md).  
  
 `pAssemblyID`  
 Puntero al identificador del ensamblado resultante.  
  
## <a name="return-value"></a>Valor devuelto  

 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 Requiere ALink. h.  
  
## <a name="see-also"></a>Vea también

- [IALink (Interfaz)](ialink-interface.md)
- [IALink2 (Interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
