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
- IAsssemblyCacheItem::CreateStream method [.NET Framework fusion]
ms.assetid: 697ab0f4-470c-4baa-a415-4a975c42d0d5
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 8057406552525be19f8e6457de9faf841edc6e68
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
ms.locfileid: "33429506"
---
# <a name="iassemblycacheitemcreatestream-method"></a>IAssemblyCacheItem::CreateStream (Método)
Crea una secuencia con el nombre especificado y el formato.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT CreateStream (  
    [in]  DWORD dwFlags,  
    [in]  LPCWSTR pszStreamName,  
    [in]  DWORD dwFormat,  
    [in]  DWORD dwFormatFlags,  
    [out] IStream **ppIStream,  
    [in, optional] ULARGE_INTEGER *puliMaxSize  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `dwFlags`  
 [in] Marcadores definidos en Fusion.idl.  
  
 `pszStreamName`  
 [in] El nombre de la secuencia que se va a crear.  
  
 `dwFormat`  
 [in] El formato del archivo que se transmite por secuencias.  
  
 `dwFormatFlags`  
 [in] Indicadores específicos del formato definidos en Fusion.idl.  
  
 `ppIStream`  
 [out] Un puntero a la dirección de devuelto [IStream](https://msdn.microsoft.com/library/aa380034.aspx) instancia.  
  
 `puliMaxSize`  
 [in, opcional] El tamaño máximo de la secuencia al que hace referencia `ppIStream`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Fusion.h  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IAssemblyCacheItem (interfaz)](../../../../docs/framework/unmanaged-api/fusion/iassemblycacheitem-interface.md)
