---
title: "CreateCoreClrDebugTarget (Función)"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CreateCorClrDebugTarget
api_location: mscordbi_macx86.dll
api_type: COM
f1_keywords: CreateCoreClrDebugTarget
helpviewer_keywords:
- remote debugging API [Silverlight]
- Silverlight, remote debugging
- CreateCoreClrDebugTarget function
ms.assetid: 1cf4ca8e-d9bb-4633-9adf-5e24315bf87a
topic_type: apiref
caps.latest.revision: "4"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: d1f52bddb5d5f11d36fcf8b833dd6fe65f9c0a4c
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/18/2017
---
# <a name="createcoreclrdebugtarget-function"></a>CreateCoreClrDebugTarget (Función)
Crea una conexión a un proxy del depurador que se ejecuta en un equipo remoto y devuelve un [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) objeto que puede utilizarse para consultar procesos en ejecución y tiempos de ejecución cargados en el equipo remoto.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateCoreClrDebugTarget (  
       [in]  DWORD    dwAddress,   
       [out] ICoreClrDebugTarget**     ppTarget  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `dwAddress`  
 [in] Dirección IPv4 de un equipo de destino remoto.  
  
 `ppTarget`  
 [out] Puntero a un puntero a un [ICoreClrDebugTarget](../../../../docs/framework/unmanaged-api/debugging/icoreclrdebugtarget-interface.md) objeto que se va a crear.  
  
## <a name="return-value"></a>Valor devuelto  
 S_OK  
 El número de CLR en el proceso se determinó correctamente y las matrices de ruta de acceso y el identificador correspondiente se rellenaron de forma adecuada.  
  
 E_OUTOFMEMORY  
 No se puede asignar memoria suficiente para `ppTarget`.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 Otros errores.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** CoreClrRemoteDebuggingInterfaces.h  
  
 **Biblioteca:** mscordbi_macx86.dll  
  
 **Versiones de .NET framework:** 3.5 SP1
