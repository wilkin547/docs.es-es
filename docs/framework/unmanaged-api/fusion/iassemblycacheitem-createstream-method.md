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
ms.openlocfilehash: 0660621f465f2ba3610e06bd1df38baa1bc5c907
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134470"
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
[in, Optional] Tamaño máximo de la secuencia a la que hace referencia `ppIStream`.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** Fusion. h

**Versiones de .NET Framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]

## <a name="see-also"></a>Vea también

- [IAssemblyCacheItem (interfaz)](iassemblycacheitem-interface.md)
