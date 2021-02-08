---
description: 'Más información acerca de: ClrCreateManagedInstance ((función)'
title: ClrCreateManagedInstance (Función)
ms.date: 03/30/2017
api_name:
- ClrCreateManagedInstance
api_location:
- mscoree.dll
- clr.dll
- mscorwks.dll
- mscoreei.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- ClrCreateManagedInstance
helpviewer_keywords:
- ClrCreateManagedInstance function [.NET Framework hosting]
ms.assetid: 58ba42c0-4857-43bf-a039-73a4dc6544c2
topic_type:
- apiref
ms.openlocfilehash: b6d3b014f54dd563e53cd8a4c48907d01945015f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799935"
---
# <a name="clrcreatemanagedinstance-function"></a>ClrCreateManagedInstance (Función)

Crea una instancia del tipo administrado especificado.  
  
 Esta función está en desuso en el .NET Framework 4. Use la activación COM para crear una instancia del tipo administrado o use el hospedaje (consulte [interfaces de hospedaje de CLR agregadas en los .NET Framework 4 y 4,5](clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
STDAPI ClrCreateManagedInstance (  
    [in]  LPCWSTR  pTypeName,
    [in]  REFIID   riid,
    [out] void     **ppObject  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `pTypeName`  
 de Puntero al nombre del tipo de instancia que se va a solicitar.  
  
 `riid`  
 de `IID` Del tipo de instancia que se solicita.  
  
 `ppObject`  
 enuncia Un puntero a un puntero a una instancia del tipo administrado solicitado por el autor de la llamada.  
  
## <a name="remarks"></a>Observaciones  

 El Common Language Runtime debe estar ya cargado en un proceso. Por ejemplo, se puede cargar mediante una llamada a la función [CorBindToRuntimeEx](corbindtoruntimeex-function.md) antes de que `ClrCreateManagedInstance` se llame a la función. Si no se carga el tiempo de ejecución, `ClrCreateManagedInstance` primero intenta cargar v 1.0.3705 del tiempo de ejecución. Si se produce un error, intenta cargar la versión más reciente del Runtime.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
- [Hospedar aplicaciones de WPF](index.md)
