---
description: 'Más información sobre: método SetPEKind ('
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
ms.openlocfilehash: 4154e9e80b7f88b6951c9aa8da5fc23d340c96dc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99662304"
---
# <a name="setpekind-method"></a>SetPEKind (Método)

Determina el tipo portable ejecutable, ya sea específico del equipo o independiente del equipo.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT SetPEKind(  
    mdAssembly AssemblyID,  
    mdToken FileToken,  
    DWORD dwPEKind,  
    DWORD dwMachine  
) PURE;
```  
  
## <a name="parameters"></a>Parámetros  

 `AssemblyID`  
 IDENTIFICADOR del ensamblado.  
  
 `FileToken`  
 Token del archivo para el que se va a establecer el tipo de PE. Puede ser NULL si `AssemblyID` no indica un valor de netmodule sin enlazar.  
  
 `dwPEKind`  
 Tipo de PE, como indica la [enumeración CorPEKind (](../metadata/corpekind-enumeration.md).  
  
 `dwMachine`  
 La arquitectura del equipo de destino, como se indica en el encabezado NT.  
  
## <a name="return-value"></a>Valor devuelto  

 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 Requiere ALink. h.  
  
## <a name="see-also"></a>Vea también

- [Método GetPEKind](../metadata/imetadataimport2-getpekind-method.md)
- [IALink2 (Interfaz)](ialink2-interface.md)
- [IALink (Interfaz)](ialink-interface.md)
- [API de ALink](index.md)
