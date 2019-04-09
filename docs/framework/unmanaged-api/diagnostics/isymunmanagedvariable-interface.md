---
title: ISymUnmanagedVariable (Interfaz)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedVariable
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedVariable
helpviewer_keywords:
- ISymUnmanagedVariable interface [.NET Framework debugging]
ms.assetid: 704c69ba-77bc-40d7-8c0c-400061686321
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 712eca7f3f9fec9c81e638802f5a664ec6469d53
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164351"
---
# <a name="isymunmanagedvariable-interface"></a>ISymUnmanagedVariable (Interfaz)
Representa una variable, como un parámetro, una variable local o un campo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetAddressField1](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|Obtiene el primer campo de dirección de esta variable. Su significado depende del tipo de dirección.|  
|[Método GetAddressField2](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|Obtiene el segundo campo de dirección de esta variable. Su significado depende del tipo de dirección.|  
|[Método GetAddressField3](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|Obtiene el tercer campo de dirección de esta variable. Su significado depende del tipo de dirección.|  
|[Método GetAddressKind](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|Obtiene el tipo de dirección de esta variable.|  
|[Método GetAttributes](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|Obtiene los marcadores de atributo para esta variable.|  
|[Método GetEndOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|Obtiene el desplazamiento final de esta variable dentro de su elemento primario.|  
|[Método GetName](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|Obtiene el nombre de esta variable.|  
|[Método GetSignature](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|Obtiene la firma de esta variable.|  
|[Método GetStartOffset](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|Obtiene el desplazamiento inicial de esta variable dentro de su elemento primario.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado**: CorSym.idl, CorSym.h  
  
## <a name="see-also"></a>Vea también

- [Interfaces de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
