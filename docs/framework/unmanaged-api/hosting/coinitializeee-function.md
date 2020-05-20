---
title: CoInitializeEE (Función)
ms.date: 03/30/2017
api_name:
- CoInitializeEE
api_location:
- mscoree.dll
- mscorsvr.dll
api_type:
- DLLExport
f1_keywords:
- CoInitializeEE
helpviewer_keywords:
- CoInitializeEE function [.NET Framework hosting]
ms.assetid: 7e42a928-5068-4ba6-b8c3-806551a01fa8
topic_type:
- apiref
ms.openlocfilehash: 57508a2df3a49c39d25347f2a3038442c37278da
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/19/2020
ms.locfileid: "83616767"
---
# <a name="coinitializeee-function"></a>CoInitializeEE (Función)
Garantiza que el motor de ejecución de Common Language Runtime se carga en un proceso. Esta función está en desuso en el .NET Framework 4. Use en su lugar el método [ICLRRuntimeHost:: Start](iclrruntimehost-start-method.md) .  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT CoInitializeEE (  
   [in] DWORD fFlags  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `fFlags`  
 de Una de las constantes de enumeración [coinitiee (](../metadata/coinitiee-enumeration.md) .  
  
## <a name="return-value"></a>Valor devuelto  
 Este método devuelve los códigos de error COM estándar, tal y como se define en Winerror. h, y los valores de la tabla siguiente.  
  
|Código de retorno|Descripción|  
|-----------------|-----------------|  
|S_OK|El motor de ejecución se cargó correctamente.|  
|S_FALSE|El motor de ejecución ya está cargado.|  
|E_FAIL|No se pudo cargar el motor de ejecución.|  
  
## <a name="remarks"></a>Observaciones  
 Este método carga el motor de ejecución si no se ha cargado previamente.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulta también

- [Funciones estáticas globales para metadatos](../metadata/metadata-global-static-functions.md)
