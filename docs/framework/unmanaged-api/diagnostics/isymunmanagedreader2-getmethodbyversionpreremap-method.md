---
title: ISymUnmanagedReader2::GetMethodByVersionPreRemap (Método)
ms.date: 03/30/2017
api_name:
- ISymUnmanagedReader2.GetMethodByVersionPreRemap
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- ISymUnmanagedReader2::GetMethodByVersionPreRemap
helpviewer_keywords:
- GetMethodByVersionPreRemap method [.NET Framework debugging]
- ISymUnmanagedReader2::GetMethodByVersionPreRemap method [.NET Framework debugging]
ms.assetid: 0d144ed4-bdb0-4cac-960c-cb90f4dca173
topic_type:
- apiref
ms.openlocfilehash: 5484242562deaf463b7435ad4e54735a7abee45e
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95730492"
---
# <a name="isymunmanagedreader2getmethodbyversionpreremap-method"></a>ISymUnmanagedReader2::GetMethodByVersionPreRemap (Método)

Obtiene un método del lector de símbolos, dado un token de método y un número de versión de edición y continuación. Los números de versión se inician en 1 y se incrementan cada vez que se cambia el método como resultado de una operación de editar y continuar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetMethodByVersionPreRemap(  
    [in]  mdMethodDef token,  
    [in]  int version,  
    [out, retval] ISymUnmanagedMethod** pRetVal);  
```  
  
## <a name="parameters"></a>Parámetros  

 `token`  
 de Token de metadatos del método.  
  
 `version`  
 de Versión del método.  
  
 `pRetVal`  
 enuncia Puntero a la interfaz [ISymUnmanagedMethod](isymunmanagedmethod-interface.md) devuelta.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK si el método se ejecuta correctamente; de lo contrario, E_FAIL u otro código de error.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl. CorSym. h  
  
## <a name="see-also"></a>Consulte también

- [ISymUnmanagedReader2 (Interfaz)](isymunmanagedreader2-interface.md)
