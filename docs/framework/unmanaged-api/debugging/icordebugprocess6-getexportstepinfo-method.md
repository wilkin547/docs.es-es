---
title: Método ICorDebugProcess6::GetExportStepInfo
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: e2c04672e51ffb16043b14735cd5375073194c27
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95732624"
---
# <a name="icordebugprocess6getexportstepinfo-method"></a>Método ICorDebugProcess6::GetExportStepInfo

Proporciona información sobre las funciones exportadas en tiempo de ejecución para ayudar a recorrer el código administrado.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetExportStepInfo(  
    [in] LPCWSTR pszExportName,
    [out] CorDebugCodeInvokeKind* pInvokeKind,
    [out] CorDebugCodeInvokePurpose* pInvokePurpose);  
```  
  
## <a name="parameters"></a>Parámetros  

 pszExportName  
 [in] Nombre de una función de exportación en tiempo de ejecución según aparece escrito en la tabla de exportación de PE.  
  
 invokeKind  
 enuncia Un puntero a un miembro de la enumeración [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) que describe cómo la función exportada llamará al código administrado.  
  
 invokePurpose  
 enuncia Un puntero a un miembro de la enumeración [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) que describe por qué la función exportada llamará al código administrado.  
  
## <a name="return-value"></a>Valor devuelto  

 El método puede devolver los valores enumerados en la siguiente tabla.  
  
|Valor devuelto|Descripción|  
|------------------|-----------------|  
|`S_OK`|La llamada al método se realizó correctamente.|  
|`E_POINTER`|`pInvokeKind` o `pInvokePurpose` es **null**.|  
|Otros valores de error de `HRESULT`.|Según el caso.|  
  
## <a name="remarks"></a>Comentarios  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **.NET Framework versiones:**[!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Interfaz ICorDebugProcess6](icordebugprocess6-interface.md)
- [Interfaces para depuración](debugging-interfaces.md)
