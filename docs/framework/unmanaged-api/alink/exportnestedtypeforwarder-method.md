---
description: 'Más información sobre: método Exportnestedtypeforwarder ('
title: ExportNestedTypeForwarder (Método)
ms.date: 03/30/2017
api_name:
- IALink.ExportNestedTypeForwarder
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- ExportNestedTypeForwarder
helpviewer_keywords:
- ExportNestedTypeForwarder method
ms.assetid: 886ea6c5-6b26-4b88-8bf6-448d6d191950
topic_type:
- apiref
ms.openlocfilehash: fd791e3fea76338f191fcf924d56720d257d2e8b
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638111"
---
# <a name="exportnestedtypeforwarder-method"></a>ExportNestedTypeForwarder (Método)

Agrega un reenviador de tipos para un tipo anidado a la tabla de tipos del ensamblado especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT ExportNestedTypeForwarder(  
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
 Token de archivo o ID. de ensamblado del archivo que define el tipo.  
  
 `TypeToken`  
 Token para el tipo.  
  
 `ParentType`  
 Token del tipo primario.  
  
 `pszTypename`  
 Nombre completo del tipo que se va a exportar.  
  
 `dwFlags`  
 `ComType` marcas como `tdPublic` o `tdNested` .  
  
 `pType`  
 Recibe el token del tipo de exportación. Esto solo es necesario para emitir tipos anidados.  
  
## <a name="return-value"></a>Valor devuelto  

 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 Requiere ALink. h  
  
## <a name="see-also"></a>Vea también

- [IALink (Interfaz)](ialink-interface.md)
- [IALink2 (Interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
