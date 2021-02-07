---
description: 'Más información acerca de: Strongnamegetblob ((función)'
title: StrongNameGetBlob (Función)
ms.date: 03/30/2017
api_name:
- StrongNameGetBlob
api_location:
- mscoree.dll
api_type:
- DLLExport
f1_keywords:
- StrongNameGetBlob
helpviewer_keywords:
- StrongNameGetBlob function [.NET Framework strong naming]
ms.assetid: 15d09166-be00-4696-913f-2c1fbc7ac2e1
topic_type:
- apiref
ms.openlocfilehash: 72f7ce50ce6170a23e5b24b68f911ff58bebe3bc
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99736445"
---
# <a name="strongnamegetblob-function"></a>StrongNameGetBlob (Función)

Llena el búfer especificado con la representación binaria del archivo ejecutable en la dirección especificada.  
  
 Esta función está en desuso. Use el método [ICLRStrongName:: strongnamegetblob (](../hosting/iclrstrongname-strongnamegetblob-method.md) en su lugar.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
BOOLEAN StrongNameGetBlob (  
    [in]  LPCWSTR    wszFilePath,  
    [in]  BYTE       *pbBlob,  
    [in, out] DWORD  *pcbBlob  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `wszFilePath`  
 de Ruta de acceso válida al archivo ejecutable que se va a cargar.  
  
 `pbBlob`  
 de Búfer en el que se va a cargar el archivo ejecutable.  
  
 `pcbBlob`  
 [in, out] Tamaño máximo solicitado, en bytes, de `pbBlob` . Después de la devolución, el tamaño real, en bytes, de `pbBlob` .  
  
## <a name="return-value"></a>Valor devuelto  

 `true` Cuando se complete correctamente; en caso contrario, `false` .  
  
## <a name="remarks"></a>Observaciones  

 Si la `StrongNameGetBlob` función no se completa correctamente, llame a la función [StrongNameErrorInfo (](strongnameerrorinfo-function.md) para recuperar el último error generado.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** StrongName. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [Método StrongNameGetBlob](../hosting/iclrstrongname-strongnamegetblob-method.md)
- [Método StrongNameGetBlobFromImage](../hosting/iclrstrongname-strongnamegetblobfromimage-method.md)
- [ICLRStrongName (Interfaz)](../hosting/iclrstrongname-interface.md)
