---
title: IMetaDataDispenserEx::GetOption (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.GetOption
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::GetOption
helpviewer_keywords:
- GetOption method [.NET Framework metadata]
- IMetaDataDispenserEx::GetOption method [.NET Framework metadata]
ms.assetid: d7f794e5-8e25-4d65-850a-7c34fbfce87d
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: a117fcdf2ba9d37fb5483cc85fb575e5d3476794
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="imetadatadispenserexgetoption-method"></a>IMetaDataDispenserEx::GetOption (Método)
Obtiene el valor de la opción especificada para el ámbito de metadatos actual. La opción controla cómo se administran las llamadas al ámbito de metadatos actual.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetOption (  
    [in]  REFGUID         optionId,   
    [out] const VARIANT   *pValue  
);  
```  
  
#### <a name="parameters"></a>Parámetros  
 `optionId`  
 [in] Un puntero a un GUID que especifica la opción que se va a recuperar. Vea la sección Comentarios para obtener una lista de identificadores GUID admitidos.  
  
 `pValue`  
 [out] El valor de la opción devuelta. El tipo de este valor será una variante del tipo de la opción especificada.  
  
## <a name="remarks"></a>Comentarios  
 En la lista siguiente se muestra los GUID que son compatibles con este método. Para obtener descripciones, consulte el [IMetaDataDispenserEx:: SetOption](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-setoption-method.md) método. Si `optionId` es no está en esta lista, este método devuelve HRESULT `E_INVALIDARG`, que indica un parámetro incorrecto.  
  
-   MetaDataCheckDuplicatesFor  
  
-   MetaDataRefToDefCheck  
  
-   MetaDataNotificationForTokenMovement  
  
-   MetaDataSetENC  
  
-   MetaDataErrorIfEmitOutOfOrder  
  
-   MetaDataGenerateTCEAdapters  
  
-   MetaDataLinkerOptions  
  
## <a name="requirements"></a>Requisitos  
 **Plataforma:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MsCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataDispenserEx (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenserex-interface.md)  
 [IMetaDataDispenser (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadatadispenser-interface.md)
