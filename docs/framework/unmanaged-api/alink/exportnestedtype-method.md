---
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
ms.openlocfilehash: 9ca2167e66ac3aa5bcc0e92ff357eed18d366c67
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79179413"
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
 ID de ensamblado desde el que exportar.  
  
 `FileToken`  
 Token de archivo o ensamblado de archivo que define el tipo que se va a exportar.  
  
 `TypeToken`  
 Escriba el token de tipo que se va a exportar.  
  
 `ParentType`  
 Token de tipo primario.  
  
 `pszTypename`  
 Nombre de tipo completo para exportar.  
  
 `dwFlags`  
 `ComType`banderas `tdPublic` como `tdNested`o . Este valor se puede pasar al [método DefineExportedType](../metadata/imetadataassemblyemit-defineexportedtype-method.md).  
  
 `pType`  
 Recibe token para el tipo exportado.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método se realiza correctamente.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h  
  
## <a name="see-also"></a>Consulte también

- [IALink (interfaz)](ialink-interface.md)
- [IALink2 (interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
