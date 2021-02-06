---
description: 'Más información acerca de: Enumerateclrs ((función)'
title: EnumerateCLRs (Función)
ms.date: 03/30/2017
api_name:
- EnumerateCLRs
api_location:
- dbgshim.dll
api_type:
- COM
f1_keywords:
- EnumerateCLRs
helpviewer_keywords:
- debugging API [Silverlight]
- Silverlight, debugging
- EnumerateCLRs function
ms.assetid: f8d50cb3-ec4f-4529-8fe3-bd61fd28e13c
topic_type:
- apiref
ms.openlocfilehash: 75124ef1e1e8588cb3d709161c3c1119e960be9e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99637786"
---
# <a name="enumerateclrs-function"></a>EnumerateCLRs (Función)

Proporciona un mecanismo para enumerar los CLR de un proceso.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT EnumerateCLRs (  
    [in]  DWORD      debuggeePID,  
    [out] HANDLE**   ppHandleArrayOut,  
    [out] LPWSTR**   ppStringArrayOut,  
    [out] DWORD*     pdwArrayLengthOut  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `debuggeePID`  
 [in] Identificador del proceso desde el que se van a enumerar los CLR cargados.  
  
 `ppHandleArrayOut`  
 [out] Puntero a una matriz que contiene identificadores de evento que se usan para continuar el inicio de un CLR. No se garantiza que todos los identificadores de la matriz sean válidos. Si es válido, el identificador se usará como evento de inicio continuo para el tiempo de ejecución correspondiente ubicado en el mismo índice de `ppStringArrayOut`.  
  
 `ppStringArrayOut`  
 [out] Puntero a una matriz de cadenas que especifican las rutas de acceso completas a los CLR cargados en el proceso.  
  
 `pdwArrayLengthOut`  
 [out] Puntero a una DWORD que contiene la longitud de `ppHandleArrayOut` y `pdwArrayLengthOut` de igual tamaño.  
  
## <a name="return-value"></a>Valor devuelto  

 S_OK  
 Se determinó el número de CLR en el proceso y las matrices de rutas de acceso e identificadores correspondientes se rellenaron correctamente.  
  
 E_INVALIDARG  
 `ppHandleArrayOut` o `ppStringArrayOut` es NULL, o `pdwArrayLengthOut` es NULL.  
  
 E_OUTOFMEMORY  
 La función no puede asignar suficiente memoria para las matrices de identificadores y rutas de acceso.  
  
 E_FAIL (u otros códigos devueltos de E_)  
 No se pueden enumerar los CLR cargados.  
  
## <a name="remarks"></a>Observaciones  

 Para un proceso de destino identificado por `debuggeePID`, la función devuelve una matriz de rutas de acceso, `ppStringArrayOut`, a los CLR cargados en el proceso; una matriz de identificadores de eventos, `ppHandleArrayOut`, que puede contener un evento de inicio continuo para el CLR en el mismo índice; y el tamaño de las matrices, `pdwArrayLengthOut`, que especifica el número de CLR que hay cargados.  
  
 En el sistema operativo Windows, `debuggeePID` se asigna a un identificador de procesos del sistema operativo.  
  
 Esta función asigna la memoria para `ppHandleArrayOut` y `ppStringArrayOut`. Para liberar la memoria asignada, debe llamar a la [función closeclrenumeration (](closeclrenumeration-function.md).  
  
 Se puede llamar a esta función con ambos parámetros de matriz establecidos en NULL para devolver el número de los CLR en el proceso de destino. A partir de este número, un llamador puede deducir el tamaño del búfer que se creará: `(sizeof(HANDLE) * count) + (sizeof(LPWSTR) * count) + (sizeof(WCHAR*) * count * MAX_PATH)`.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** dbgshim. h  
  
 **Biblioteca:** dbgshim.dll  
  
 **.NET Framework versiones:** 3,5 SP1
