---
description: 'Más información acerca de: ISymUnmanagedWriter:: Openmethod ((método)'
title: ISymUnmanagedWriter::OpenMethod (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter.OpenMethod
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter::OpenMethod
helpviewer_keywords:
- ISymUnmanagedWriter::OpenMethod method [.NET Framework debugging]
- OpenMethod method [.NET Framework debugging]
ms.assetid: fb90cb7f-af88-45e8-a99f-80a0bbddb08b
topic_type:
- apiref
ms.openlocfilehash: 2cf7e6bf7c632449c25a2b49c7658fa7b1cc287e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99762232"
---
# <a name="isymunmanagedwriteropenmethod-method"></a>ISymUnmanagedWriter::OpenMethod (Método)

Abre un método en el que se emite información de símbolos. El método especificado se convierte en el método actual para que las llamadas definan los puntos de secuencia, los parámetros y los ámbitos léxicos. Hay un ámbito léxico implícito en torno al método completo. Al volver a abrir un método que se cerró previamente, se borran los símbolos definidos previamente para ese método. Solo puede haber un método abierto a la vez.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT OpenMethod(  
    [in] mdMethodDef method);  
```  
  
## <a name="parameters"></a>Parámetros  

 `method`  
 de Símbolo (token) de metadatos para el método que se va a abrir.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Vea también

- [ISymUnmanagedWriter (Interfaz)](isymunmanagedwriter-interface.md)
- [Método CloseMethod](isymunmanagedwriter-closemethod-method.md)
- [Método OpenMethod2](isymunmanagedwriter3-openmethod2-method.md)
