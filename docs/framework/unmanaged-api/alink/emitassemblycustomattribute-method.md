---
description: 'Más información sobre: método Emitassemblycustomattribute ('
title: EmitAssemblyCustomAttribute (Método)
ms.date: 03/30/2017
api_name:
- IALink.EmitAssemblyCustomAttribute
- EmitAssemblyCustomAttribute
api_location:
- alink.dll
api_type:
- COM
f1_keywords:
- EmitAssemblyCustomAttribute
helpviewer_keywords:
- EmitAssemblyCustomAttribute method
ms.assetid: b72f5409-79af-4fa7-90a7-7630eec170f1
topic_type:
- apiref
ms.openlocfilehash: c91eb563c14b442a22db8f328287c10e5cc9a63c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638332"
---
# <a name="emitassemblycustomattribute-method"></a>EmitAssemblyCustomAttribute (Método)

Llame a para establecer los atributos personalizados de nivel de ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EmitAssemblyCustomAttribute(  
    mdAssembly   AssemblyID,  
    mdToken      FileToken,  
    mdToken      tkType,  
    void const*  pCustomValue,  
    DWORD        cbCustomValue,  
    BOOL         bSecurity,  
    BOOL         bAllowMulti  
) PURE;  
```  
  
## <a name="parameters"></a>Parámetros  

 `AssemblyID`  
 IDENTIFICADOR del ensamblado.  
  
 `FileToken`  
 Archivo que Desarchiva el atributo. Puede ser NULL si `AssemblyID` no indica un valor de netmodule sin enlazar.  
  
 `tkType`  
 Tipo del atributo personalizado.  
  
 `pCustomValue`  
 Datos de valores personalizados.  
  
 `cbCustomValue`  
 Longitud de los datos de valor personalizados.  
  
 `bSecurity`  
 TRUE si el atributo personalizado está relacionado con la firma de ensamblados.  
  
 `bAllowMulti`  
 TRUE si se van a emitir varios atributos.  
  
## <a name="return-value"></a>Valor devuelto  

 Devuelve S_OK si el método se ejecuta correctamente.  
  
## <a name="requirements"></a>Requisitos  

 Requiere ALink. h  
  
## <a name="see-also"></a>Vea también

- [IALink (Interfaz)](ialink-interface.md)
- [IALink2 (Interfaz)](ialink2-interface.md)
- [API de ALink](index.md)
