---
title: Método ICorDebugProcess6::GetExportStepInfo
ms.date: 03/30/2017
ms.assetid: a927e0ac-f110-426d-bbec-9377a29c8f17
ms.openlocfilehash: 6580fdaacaea17fcf886bfd7ac5e236925acf453
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79178533"
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
 [fuera] Puntero a un miembro de la [CorDebugCodeInvokeKind](cordebugcodeinvokekind-enumeration.md) enumeración que describe cómo la función exportada invocará código administrado.  
  
 invokePurpose  
 [fuera] Un puntero a un miembro de la [CorDebugCodeInvokePurpose](cordebugcodeinvokepurpose-enumeration.md) enumeración que describe por qué la función exportada llamará a código administrado.  
  
## <a name="return-value"></a>Valor devuelto  
 El método puede devolver los valores enumerados en la siguiente tabla.  
  
|Valor devuelto|Descripción|  
|------------------|-----------------|  
|`S_OK`|La llamada al método se realizó correctamente.|  
|`E_POINTER`|`pInvokeKind`o `pInvokePurpose` es **nulo**.|  
|Otros valores de error de `HRESULT`.|Según el caso.|  
  
## <a name="remarks"></a>Observaciones  
  
> [!NOTE]
> Este método solo está disponible con .NET Native.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CorDebug.idl, CorDebug.h  
  
 **Biblioteca:** CorGuids.lib  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_46_native](../../../../includes/net-46-native-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [ICorDebugProcess6 (interfaz)](icordebugprocess6-interface.md)
- [Interfaces de depuración](debugging-interfaces.md)
