---
title: SetPEKind (Método)
ms.date: 03/30/2017
api_name:
- IALink2.SetPEKind
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- SetPEKind
helpviewer_keywords:
- SetPEKind method
ms.assetid: 050e77ee-3014-45c0-9e29-2ebe29347b0d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 4b985aeb97621e552e9e97581e67cae029d019ef
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="setpekind-method"></a>SetPEKind (Método)
Determina el tipo de archivo ejecutable portable, específicas del equipo o independiente del equipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;   
```  
  
#### <a name="parameters"></a>Parámetros  
 `AssemblyID`  
 Identificador del ensamblado.  
  
 `FileToken`  
 Símbolo (token) de archivo para el que se puede establecer el tipo de PE. Puede ser NULL si `AssemblyID` no indica un archivo netmodule no enlazado.  
  
 `dwPEKind`  
 El tipo de PE, tal y como indica la [CorPEKind (enumeración)](../../../../docs/framework/unmanaged-api/metadata/corpekind-enumeration.md).  
  
 `dwMachine`  
 Arquitectura del equipo de destino, como se indica en el encabezado NT.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h.  
  
## <a name="see-also"></a>Vea también  
 [GetPEKind (método)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-getpekind-method.md)  
 [IALink2 (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
