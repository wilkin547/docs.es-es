---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod (Método)
ms.date: 03/30/2017
ms.assetid: 4662f70d-817b-4374-8da8-e0545585939f
ms.openlocfilehash: 418a77855d1cb34a07f5957059b5a6f5a106c321
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95707092"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefinekickoffmethod-method"></a>ISymUnmanagedAsyncMethodPropertiesWriter::DefineKickoffMethod (Método)

Establece el método de inicio que inicia la operación asincrónica.  
  
## <a name="syntax"></a>Sintaxis  
  
```idl  
HRESULT DefineKickoffMethod(    [in] mdToken kickoffMethod);  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|`kickoffMethod`||  
  
## <a name="return-value"></a>Valor devuelto  

 Devuelve `HRESULT`.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también

- [ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)](isymunmanagedasyncmethodpropertieswriter-interface.md)
