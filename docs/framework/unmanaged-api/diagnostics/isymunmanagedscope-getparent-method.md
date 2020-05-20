---
title: ISymUnmanagedScope::GetParent (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedScope.GetParent
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedScope::GetParent
helpviewer_keywords:
- GetParent method [.NET Framework debugging]
- ISymUnmanagedScope::GetParent method [.NET Framework debugging]
ms.assetid: c7963c87-6ec5-49b3-a5cd-e0fe0c43f9b4
topic_type:
- apiref
ms.openlocfilehash: 95ae081d61200e4fd020609a4d23783f265d2cc6
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83615363"
---
# <a name="isymunmanagedscopegetparent-method"></a>ISymUnmanagedScope::GetParent (Método)
Obtiene el ámbito primario de este ámbito.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetParent(  
    [out, retval] ISymUnmanagedScope** pRetVal);  
```  
  
## <a name="parameters"></a>Parámetros  
 `pRetVal`  
 enuncia Puntero a la interfaz [ISymUnmanagedScope](isymunmanagedscope-interface.md) devuelta.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  
 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulta también

- [ISymUnmanagedScope (Interfaz)](isymunmanagedscope-interface.md)
- [Método GetChildren](isymunmanagedscope-getchildren-method.md)
