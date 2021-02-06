---
description: 'Más información sobre: método Exportnestedtype ('
title: ExportNestedType (Método)
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedType
- ExportNestedType
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedType
helpviewer_keywords:
- ExportNestedType method
ms.assetid: dec7df60-4d30-47c8-99db-72e0419e5f76
topic_type:
- apiref
ms.openlocfilehash: 66cf4c3572857a0e7e99efa966cdb0b9ae2be673
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638149"
---
# <a name="exportnestedtype-method"></a>ExportNestedType (Método)

Especifica los tipos anidados como exportables. El [método ExportType](exporttype-method.md) también puede exportar tipos anidados, pero este método es más rápido.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ExportNestedType(  
    mdAssembly      AssemblyID,  
    mdToken         FileToken,  
    mdTypeDef       TypeToken,  
    mdExportedType  ParentType,  
    LPCWSTR         pszTypename,  
    DWORD           dwFlags,  
    mdExportedType* pType  
) PURE;
```  
  
## <a name="parameters"></a>Parámetros  

 `AssemblyID`  
 IDENTIFICADOR del ensamblado del que se va a exportar.  
  
 `FileToken`  
 Token de archivo o ensamblado de archivo que define el tipo que se va a convertir.  
  
 `TypeToken`  
 Token de tipo del tipo que se va a convertir.  
  
 `ParentType`  
 Token del tipo primario.  
  
 `pszTypename`  
 Nombre completo del tipo que se va a exportar.  
  
 `dwFlags`  
 `ComType` marcas como `tdPublic` o `tdNested` . Este valor se puede pasar al [método DefineExportedType (](../metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
 `pType`  
 Recibe el token para el tipo exportado.  
  
## <a name="return-value"></a>Valor devuelto  

 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 Requiere ALink. h  
  
## <a name="see-also"></a>Vea también

- [IALink (Interfaz)](ialink-interface.md)
- [IALink2 (Interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
