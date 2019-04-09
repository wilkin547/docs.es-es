---
title: Método IXCLRDataModule::Request
ms.date: 01/16/2019
api.name:
- IXCLRDataModule::Request Method
api.location:
- mscordacwks.dll
api.type:
- COM
f1.keywords:
- IXCLRDataModule::Request Method
helpviewer.keywords:
- IXCLRDataModule::Request Method [.NET Framework debugging]
topic_type:
- apiref
author: cshung
ms.author: andrewau
ms.openlocfilehash: a02a60668ae6caaad1940395822758331b93f550
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59119800"
---
# <a name="ixclrdatamodulerequest-method"></a>Método IXCLRDataModule::Request

Solicitudes para llenar el búfer especificado con los datos del módulo.

[!INCLUDE[debugging-api-recommended-note](../../../../includes/debugging-api-recommended-note.md)]

## <a name="syntax"></a>Sintaxis
```
HRESULT Request([in] ULONG32 reqCode,
    [in] ULONG32 inBufferSize,
    [in, size_is(inBufferSize)] BYTE* inBuffer,
    [in] ULONG32 outBufferSize,
    [out, size_is(outBufferSize)] BYTE* outBuffer);
```

## <a name="parameters"></a>Parámetros

`reqCode`\
[in] Tipo de solicitud en enviarse.

`inBufferSize`\
[in] tamaño del búfer de entrada que se pasarán en.

`inBuffer`\
[in, size_is(inBufferSize)] Puntero de búfer para los datos sin procesar que se enviarán en la solicitud.

`outBufferSize`\
[in] Tamaño del búfer de salida.

`outBuffer`\
[out, size_is(outBufferSize)] Puntero de búfer que usará para almacenar la respuesta de solicitud.

## <a name="remarks"></a>Comentarios

El método proporcionado forma parte de la `IXCLRDataModule` interfaz y corresponde a la ranura de la tabla de métodos virtuales 36th.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
**Encabezado**: Ninguna   
**Biblioteca:** Ninguna  
**Versiones de .NET Framework:** [!INCLUDE[net_current_v47plus](../../../../includes/net-current-v47plus.md)]  

## <a name="see-also"></a>Vea también

- [Depuración](index.md)
- [Interfaz IXCLRDataModule](ixclrdatamodule-interface.md)