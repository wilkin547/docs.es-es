---
description: 'Más información acerca de: Createcoreclrdebugtarget ((función)'
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
ms.openlocfilehash: 30a6af29e6e1a6ee2c827049a3c792f2d663a702
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661581"
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
  
## <a name="parameters"></a>Parámetros  

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
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** CoreClrRemoteDebuggingInterfaces. h  
  
 **Biblioteca:** mscordbi_macx86.dll  
  
 **.NET Framework versiones:** 3,5 SP1
