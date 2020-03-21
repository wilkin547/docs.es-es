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
ms.openlocfilehash: 7fbe0cf3e93d75749fa3f463f3f97dbd1bfe27a0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79176544"
---
# <a name="clrcreatemanagedinstance-function"></a>ClrCreateManagedInstance (Función)
Crea una instancia del tipo administrado especificado.  
  
 Esta función ha quedado en desuso en .NET Framework 4. Use la activación COM para crear una instancia del tipo administrado o use el hospedaje (consulte Interfaces de [hospedaje de CLR agregadas en .NET Framework 4 y 4.5](../../../../docs/framework/unmanaged-api/hosting/clr-hosting-interfaces-added-in-the-net-framework-4-and-4-5.md)).  
  
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
 [en] Puntero al nombre del tipo de instancia que se solicita.  
  
 `riid`  
 [en] El `IID` tipo de instancia que se solicita.  
  
 `ppObject`  
 [fuera] Puntero a un puntero a una instancia del tipo administrado solicitado por el autor de la llamada.  
  
## <a name="remarks"></a>Observaciones  
 Common Language Runtime ya debe cargarse en un proceso. Por ejemplo, se puede cargar mediante una llamada a la `ClrCreateManagedInstance` [función CorBindToRuntimeEx](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md) antes de llamar a la función. Si no se carga `ClrCreateManagedInstance` el tiempo de ejecución, primero intenta cargar v1.0.3705 del tiempo de ejecución. Si se produce un error, intenta cargar la versión más reciente del tiempo de ejecución.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** MScorEE.h  
  
 **Biblioteca:** Mscoree.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [Funciones de hospedaje de CLR en desuso](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)
- [Hospedaje](../../../../docs/framework/unmanaged-api/hosting/index.md)
