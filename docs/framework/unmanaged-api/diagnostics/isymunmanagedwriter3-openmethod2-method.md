---
title: ISymUnmanagedWriter3::OpenMethod2 (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedWriter3.OpenMethod2
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedWriter3::OpenMethod2
helpviewer_keywords:
- ISymUnmanagedWriter3::OpenMethod2 method [.NET Framework debugging]
- OpenMethod2 method [.NET Framework debugging]
ms.assetid: 025e358c-448f-4423-a2f2-57acf437c8a5
topic_type:
- apiref
ms.openlocfilehash: e88a844a7f79f14c717a5966b345588b3b3b9f81
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609422"
---
# <a name="isymunmanagedwriter3openmethod2-method"></a>ISymUnmanagedWriter3::OpenMethod2 (Método)
Abre un método y proporciona su desplazamiento de sección real en la imagen.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT OpenMethod2(
    [in] mdMethodDef method,  
    [in] ULONG32 isect,  
    [in] ULONG32 offset);  
```  
  
## <a name="parameters"></a>Parámetros  
 `method`  
 de Símbolo (token) de metadatos para el método que se va a abrir.  
  
 `isect`  
 de El desplazamiento de la sección en la imagen.  
  
 `offset`  
 de Desplazamiento de la imagen.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulta también

- [ISymUnmanagedWriter3 (Interfaz)](isymunmanagedwriter3-interface.md)
- [Método OpenMethod](isymunmanagedwriter-openmethod-method.md)
