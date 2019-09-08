---
title: IAssemblyCacheItem::CreateStream (Método)
ms.date: 03/30/2017
api_name:
- IAssemblyCacheItem.CreateStream
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyCacheItem::CreateStream
helpviewer_keywords:
- CreateStream method [.NET Framework fusion]
- IAssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 5af7dc4e1694b66fc4a5ce37e515c71e9fa3db49
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70796731"
---
# <a name="iassemblycacheitemcreatestream-method"></a>IAssemblyCacheItem::CreateStream (Método)

Crea una secuencia con el nombre y el formato especificados.

## <a name="syntax"></a>Sintaxis

```cpp
HRESULT CreateStream (
    [in]  DWORD dwFlags,
    [in]  LPCWSTR pszStreamName,
    [in]  DWORD dwFormat,
    [in]  DWORD dwFormatFlags,
    [out] IStream **ppIStream,
    [in, optional] ULARGE_INTEGER *puliMaxSize
);
```

## <a name="parameters"></a>Parámetros

`dwFlags`\
de Marcas definidas en Fusion. idl.

`pszStreamName`\
de Nombre del flujo que se va a crear.

`dwFormat`\
de Formato del archivo que se va a transmitir por secuencias.

`dwFormatFlags`\
de Marcas específicas del formato definidas en Fusion. idl.

`ppIStream`\
enuncia Puntero a la dirección de la instancia de [IStream](/windows/desktop/api/objidl/nn-objidl-istream) devuelta.

`puliMaxSize`\
[in, Optional] Tamaño máximo de la secuencia a `ppIStream`la que hace referencia.

## <a name="requirements"></a>Requisitos

**Select** Consulte [Requisitos del sistema](../../get-started/system-requirements.md).

**Encabezado**: Fusion. h

**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vea también

- [IAssemblyCacheItem (interfaz)](iassemblycacheitem-interface.md)
