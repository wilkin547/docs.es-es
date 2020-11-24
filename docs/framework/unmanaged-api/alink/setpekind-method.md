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
ms.openlocfilehash: be8a11cbf70e2c6f19ace67648b124515c1fb3c3
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95680045"
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
  
## <a name="see-also"></a>Consulte también

- [Método GetPEKind](../metadata/imetadataimport2-getpekind-method.md)
- [IALink2 (Interfaz)](ialink2-interface.md)
- [IALink (Interfaz)](ialink-interface.md)
- [API de ALink](index.md)
