---
title: CreateCoreClrDebugTarget (Función)
ms.date: 03/30/2017
api_name:
- CreateCorClrDebugTarget
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type:
- apiref
ms.openlocfilehash: a7fed8cb70785f0ccfcadf1e16181db303ac98e0
ms.sourcegitcommit: 13e79efdbd589cad6b1de634f5d6b1262b12ab01
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 01/28/2020
ms.locfileid: "76789195"
---
# <a name="createcoreclrdebugtarget-function"></a>CreateCoreClrDebugTarget (Función)
Crea una conexión a un proxy del depurador que se ejecuta en un equipo remoto y devuelve un objeto [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) que se puede usar para consultar los procesos en ejecución y los tiempos de ejecución cargados en el equipo remoto.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,   
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
## <a name="parameters"></a>Parameters  
 `dwAddress`  
 [in] Dirección IPv4 de un equipo de destino remoto.  
  
 `ppTarget`  
 enuncia Puntero a un puntero a un objeto [ICoreClrDebugTarget](icoreclrdebugtarget-interface.md) que se creará.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK  
 Se determinó el número de CLR en el proceso y las matrices de rutas de acceso e identificadores correspondientes se rellenaron correctamente.  
  
 E_OUTOFMEMORY  
 No se puede asignar memoria suficiente para `ppTarget`.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 Otros errores.  
  
## <a name="requirements"></a>Requisitos de  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CoreClrRemoteDebuggingInterfaces. h  
  
 **Library:** mscordbi_macx86.dll  
  
 **.NET Framework versiones:** 3,5 SP1
