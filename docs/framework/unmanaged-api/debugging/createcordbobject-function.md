---
description: 'Más información acerca de: Createcordbobject ((función)'
title: CreateCordbObject (Función)
ms.date: 03/30/2017
api_name:
- CreateCoredbObject
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCordbObject
helpviewer_keywords:
- remote debugging API [Silverlight]
- CreateCordbObject function
- Silverlight, remote debugging
ms.assetid: b259821d-4fa7-464d-85cf-304dfffc8089
topic_type:
- apiref
ms.openlocfilehash: b6a585fc89f780b22f842127e1923414dbb8230f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801480"
---
# <a name="createcordbobject-function"></a>CreateCordbObject (Función)

Crea una interfaz de depurador ([ICorDebug](icordebug-interface.md)) que proporciona funcionalidad para crear instancias de una sesión de depuración administrada en un proceso remoto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CordbCreateObject (  
       [in]  int         iDebuggerVersion,
       [out] IUnknown**  ppCordb  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `iDebuggerVersion`  
 [in] Versión de depuración del proceso de destino. Este parámetro debe ser CorDebugVersion_2_0 para la depuración remota.  
  
 `ppCordb`  
 enuncia Puntero a un puntero a un objeto que se convertirá en una interfaz [ICorDebug](icordebug-interface.md) y se devolverá.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK  
 Se determinó el número de CLR en el proceso y las matrices de rutas de acceso e identificadores correspondientes se rellenaron correctamente.  
  
 E_INVALIDARG  
 `ppCordb` es nulo o `iDebuggerVersion` no es CorDebugVersion_2_0.  
  
 E_OUTOFMEMORY  
 No se puede asignar memoria suficiente para `ppCordb`.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 Otros errores.  
  
## <a name="remarks"></a>Observaciones  

 La interfaz [ICorDebug](icordebug-interface.md) que se devuelve en `ppCordb` es la interfaz de depuración de nivel superior para todos los servicios de depuración administrados.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CoreClrRemoteDebuggingInterfaces. h  
  
 **Biblioteca:** mscordbi_macx86.dll  
  
 **.NET Framework versiones:** 3,5 SP1
