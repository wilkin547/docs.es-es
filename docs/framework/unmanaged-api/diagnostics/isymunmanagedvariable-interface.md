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
ms.openlocfilehash: ee57ba14f048032e2cd9d0129089743c0f0304bc
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74445977"
---
# <a name="isymunmanagedvariable-interface"></a>ISymUnmanagedVariable (Interfaz)
Representa una variable, como un parámetro, una variable local o un campo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[GetAddressField1 (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield1-method.md)|Obtiene el primer campo de dirección para esta variable. Su significado depende del tipo de dirección.|  
|[GetAddressField2 (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield2-method.md)|Obtiene el segundo campo de dirección para esta variable. Su significado depende del tipo de dirección.|  
|[GetAddressField3 (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddressfield3-method.md)|Obtiene el tercer campo de dirección para esta variable. Su significado depende del tipo de dirección.|  
|[GetAddressKind (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getaddresskind-method.md)|Obtiene el tipo de dirección de esta variable.|  
|[GetAttributes (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getattributes-method.md)|Obtiene las marcas de atributo para esta variable.|  
|[GetEndOffset (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getendoffset-method.md)|Obtiene el desplazamiento final de esta variable dentro de su elemento primario.|  
|[GetName (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getname-method.md)|Obtiene el nombre de esta variable.|  
|[GetSignature (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getsignature-method.md)|Obtiene la firma de esta variable.|  
|[GetStartOffset (método)](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedvariable-getstartoffset-method.md)|Obtiene el desplazamiento inicial de esta variable dentro de su elemento primario.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [Interfaces de almacén de símbolos de diagnósticos](../../../../docs/framework/unmanaged-api/diagnostics/diagnostics-symbol-store-interfaces.md)
