---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: daf2c3dcaf16e949f8770121d8324cbfe6c7d05b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33404084"
---
# <a name="emitassemblycustomattribute-method"></a>EmitAssemblyCustomAttribute (Método)
La llamada para establecer los atributos personalizados de nivel de ensamblado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
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
  
#### <a name="parameters"></a>Parámetros  
 `AssemblyID`  
 Identificador del ensamblado.  
  
 `FileToken`  
 Archivo que define el atributo. Puede ser NULL si `AssemblyID` no indica un archivo netmodule no enlazado.  
  
 `tkType`  
 Tipo del atributo personalizado.  
  
 `pCustomValue`  
 Datos del valor personalizado.  
  
 `cbCustomValue`  
 Longitud de datos del valor personalizado.  
  
 `bSecurity`  
 Es TRUE si el atributo personalizado está relacionado con la firma de un ensamblado.  
  
 `bAllowMulti`  
 Es TRUE si hay varios atributos que se emitan.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h  
  
## <a name="see-also"></a>Vea también  
 [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)  
 [IALink2 (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)  
 [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
