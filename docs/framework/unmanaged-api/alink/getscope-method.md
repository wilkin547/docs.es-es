---
title: Método GetScope
ms.date: 03/30/2017
api_name:
- IALink.GetScope
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- GetScope
helpviewer_keywords:
- GetScope method
ms.assetid: e1555328-2c71-4ece-b357-9eb6d3a8efc4
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 571612796d4e66be9dd8469d748c2380c839ddfa
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59165794"
---
# <a name="getscope-method"></a>Método GetScope
Obtiene un ámbito de importación.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetScope(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwScope,  
    IMetaDataImport** ppImportScope  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  
 `AssemblyID`  
 Identificador único del ensamblado para importar a.  
  
 `FileToken`  
 Identificador único del archivo para importar desde.  
  
 `dwScope`  
 Ámbito de base cero para importar.  
  
 `ppImportScope`  
 Recibe [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md) interfaz para el ámbito.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h  
  
## <a name="see-also"></a>Vea también

- [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2 (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
