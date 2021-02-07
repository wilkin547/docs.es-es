---
description: 'Más información sobre: IMetaDataDispenserEx:: GetCORSystemDirectory ((método)'
title: IMetaDataDispenserEx::GetCORSystemDirectory (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetCORSystemDirectory
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory
helpviewer_keywords:
- IMetaDataDispenserEx::GetCORSystemDirectory method [.NET Framework metadata]
- GetCORSystemDirectory method [.NET Framework metadata]
ms.assetid: d9e0f3b6-e106-4820-bada-5bfba34ce360
topic_type:
- apiref
ms.openlocfilehash: 3ceda653e50ba5ad7de5548b78781f48cda41624
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99753567"
---
# <a name="imetadatadispenserexgetcorsystemdirectory-method"></a>IMetaDataDispenserEx::GetCORSystemDirectory (Método)

Obtiene el directorio que contiene el Common Language Runtime actual (CLR). Este método solo se admite para su uso en depuradores fuera de proceso. Si se llama desde otro componente, devolverá E_NOTIMPL.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetCORSystemDirectory (  
    [out] LPWSTR      szBuffer,
    [in]  DWORD       cchBuffer,
    [out] DWORD*      pchBuffer  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `szBuffer`  
 enuncia Búfer en el que se va a recibir el nombre del directorio.  
  
 `cchBuffer`  
 de Tamaño, en bytes, de `szBuffer` .  
  
 `pchBuffer`  
 enuncia Número de bytes devueltos realmente en `szBuffer` .  
  
## <a name="requirements"></a>Requisitos  

 **Plataforma:** Consulte [requisitos del sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataDispenserEx (Interfaz)](imetadatadispenserex-interface.md)
- [IMetaDataDispenser (Interfaz)](imetadatadispenser-interface.md)
