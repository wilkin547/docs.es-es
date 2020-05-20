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
ms.openlocfilehash: d05d4451e8fb75829b22e0a1b9c9afcb0607eb8b
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83610176"
---
# <a name="isymunmanagedvariable-interface"></a>ISymUnmanagedVariable (Interfaz)
Representa una variable, como un parámetro, una variable local o un campo.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método GetAddressField1](isymunmanagedvariable-getaddressfield1-method.md)|Obtiene el primer campo de dirección para esta variable. Su significado depende del tipo de dirección.|  
|[Método GetAddressField2](isymunmanagedvariable-getaddressfield2-method.md)|Obtiene el segundo campo de dirección para esta variable. Su significado depende del tipo de dirección.|  
|[Método GetAddressField3](isymunmanagedvariable-getaddressfield3-method.md)|Obtiene el tercer campo de dirección para esta variable. Su significado depende del tipo de dirección.|  
|[Método GetAddressKind](isymunmanagedvariable-getaddresskind-method.md)|Obtiene el tipo de dirección de esta variable.|  
|[Método GetAttributes](isymunmanagedvariable-getattributes-method.md)|Obtiene las marcas de atributo para esta variable.|  
|[GetEndOffset (Método)](isymunmanagedvariable-getendoffset-method.md)|Obtiene el desplazamiento final de esta variable dentro de su elemento primario.|  
|[Método GetName](isymunmanagedvariable-getname-method.md)|Obtiene el nombre de esta variable.|  
|[GetSignature (Método)](isymunmanagedvariable-getsignature-method.md)|Obtiene la firma de esta variable.|  
|[Método GetStartOffset](isymunmanagedvariable-getstartoffset-method.md)|Obtiene el desplazamiento inicial de esta variable dentro de su elemento primario.|  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulta también

- [Interfaces de almacén de símbolos de diagnósticos](diagnostics-symbol-store-interfaces.md)
