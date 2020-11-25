---
title: ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo (Método)
ms.date: 03/30/2017
ms.assetid: f738a6ed-7cd9-4106-a5cd-355481e5771c
ms.openlocfilehash: f8c77e44183fd92704aa91ca1cfd7e3fa68aa27f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95719624"
---
# <a name="isymunmanagedasyncmethodpropertieswriterdefineasyncstepinfo-method"></a>ISymUnmanagedAsyncMethodPropertiesWriter::DefineAsyncStepInfo (Método)

Defina un grupo de operaciones de espera asincrónica en el método actual.  
  
 Cada desplazamiento yield coincide con una instrucción return de Await, que identifica un posible rendimiento. Cada `breakpointMethod` / `breakpointOffset` par nos indica dónde se reanudará la operación asincrónica, que podría estar en un método diferente.  
  
## <a name="syntax"></a>Sintaxis  
  
```idl  
HRESULT DefineAsyncStepInfo(    [in] ULONG32 count,    [in, size_is(count)] ULONG32 yieldOffsets[],    [in, size_is(count)] ULONG32 breakpointOffset[],     [in, size_is(count)] mdToken breakpointMethod[]);  
```  
  
## <a name="parameters"></a>Parámetros  
  
|Parámetro|Descripción|  
|---------------|-----------------|  
|`count`||  
|`yieldOffsets`||  
|`breakpointOffset`||  
|`breakpointMethod`||  
  
## <a name="return-value"></a>Valor devuelto  

 Devuelve `HRESULT`.  
  
## <a name="requirements"></a>Requisitos  

 **Encabezado:** CorSym. idl, CorSym. h  
  
## <a name="see-also"></a>Consulte también

- [ISymUnmanagedAsyncMethodPropertiesWriter (Interfaz)](isymunmanagedasyncmethodpropertieswriter-interface.md)
