---
title: Método ISOSDacInterface::GetMethodDescData
ms.date: 01/16/2019
api.name:
- ISOSDacInterface::GetMethodDescData Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- ISOSDacInterface::GetMethodDescData Method
helpviewer.keywords:
- ISOSDacInterface::GetMethodDescData Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: 47cea4810b764005e87d00966c15cf138f5913a7
ms.sourcegitcommit: 3500c4845f96a91a438a02ef2c6b4eef45a5e2af
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/07/2019
ms.locfileid: "55825958"
---
# <a name="isosdacinterfacegetmethoddescdata-method"></a>Método ISOSDacInterface::GetMethodDescData

Obtiene los datos para el puntero de MethodDesc determinado.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis

```
HRESULT GetMethodDescData(
    CLRDATA_ADDRESS            methodDesc,
    CLRDATA_ADDRESS            ip,
    DacpMethodDescData *data,
    ULONG                      cRevertedRejitVersions,
    DacpReJitData      *rgRevertedRejitData,
    void                      *pcNeededRevertedRejitData
);
```

### <a name="parameters"></a>Parámetros

`methodDesc` [in] La dirección de la MethodDesc.

`ip` [in] La dirección IP del método.

`data` [out] Los datos asociados con el MethodDesc devuelto desde las API internas.

`cRevertedRejitVersions` [out] El número de versiones de rejit revertida.

`rgRevertedRejitData` [out] Los datos asociados con las versiones de rejit revertida devuelto desde las API internas.

`pcNeededRevertedRejitData` [out] El número de bytes necesarios para almacenar los datos asociados con las versiones de ReJit revertidas.

## <a name="remarks"></a>Comentarios

El método proporcionado forma parte de la `ISOSDacInterface` interfaz y corresponde a la ranura de la tabla de métodos virtuales 20. Para poder utilizarlos, [ `CLRDATA_ADDRESS` ](../common-data-types-unmanaged-api-reference.md) debe definirse como un entero de 64 bits sin signo.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado**: Ninguna  
**Biblioteca:** Ninguna  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](../../../../docs/framework/unmanaged-api/debugging/index.md)
- [Interfaz ISOSDacInterface](../../../../docs/framework/unmanaged-api/debugging/isosdacinterface-interface.md)
