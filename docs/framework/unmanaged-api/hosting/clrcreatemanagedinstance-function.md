---
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
ms.openlocfilehash: 9aed79138499f1aa7b6fa3a28ad4505edd51b041
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95731779"
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
  
## <a name="remarks"></a>Comentarios  

 El Common Language Runtime debe estar ya cargado en un proceso. Por ejemplo, se puede cargar mediante una llamada a la función [CorBindToRuntimeEx](corbindtoruntimeex-function.md) antes de que `ClrCreateManagedInstance` se llame a la función. Si no se carga el tiempo de ejecución, `ClrCreateManagedInstance` primero intenta cargar v 1.0.3705 del tiempo de ejecución. Si se produce un error, intenta cargar la versión más reciente del Runtime.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** MSCorEE. h  
  
 **Biblioteca:** MSCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Funciones de hospedaje de CLR en desuso](deprecated-clr-hosting-functions.md)
- [Hospedar aplicaciones de WPF](index.md)
