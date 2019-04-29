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
ms.openlocfilehash: 67073f04cfe981dd383369029d9a4b436929a0a6
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/23/2019
ms.locfileid: "61790031"
---
# <a name="emitassemblycustomattribute-method"></a>EmitAssemblyCustomAttribute (Método)
Llamada para establecer los atributos personalizados de nivel de ensamblado.  
  
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
  
## <a name="parameters"></a>Parámetros  
 `AssemblyID`  
 Id. del ensamblado.  
  
 `FileToken`  
 Archivo que define el atributo. Puede ser NULL si `AssemblyID` no indica un netmodule independiente.  
  
 `tkType`  
 Tipo del atributo personalizado.  
  
 `pCustomValue`  
 Datos del valor personalizado.  
  
 `cbCustomValue`  
 Longitud de datos de valor personalizado.  
  
 `bSecurity`  
 TRUE si el atributo personalizado está relacionado con la firma de ensamblados.  
  
 `bAllowMulti`  
 TRUE si deben emitirse varios atributos.  
  
## <a name="return-value"></a>Valor devuelto  
 Devuelve S_OK si el método tiene éxito.  
  
## <a name="requirements"></a>Requisitos  
 Requiere alink.h  
  
## <a name="see-also"></a>Vea también

- [IALink (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink-interface.md)
- [IALink2 (interfaz)](../../../../docs/framework/unmanaged-api/alink/ialink2-interface.md)
- [API de ALink](../../../../docs/framework/unmanaged-api/alink/index.md)
