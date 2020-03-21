---
title: IMetaDataImport::GetEventProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetEventProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetEventProps
helpviewer_keywords:
- IMetaDataImport::GetEventProps method [.NET Framework metadata]
- GetEventProps method [.NET Framework metadata]
ms.assetid: 5eaf3b4a-92b7-4d5b-97e0-1e83721e0052
topic_type:
- apiref
ms.openlocfilehash: 306c1748b4997309ee15fb7751bc818b0287aaf0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/12/2020
ms.locfileid: "79177267"
---
# <a name="imetadataimportgeteventprops-method"></a>IMetaDataImport::GetEventProps (Método)
Obtiene información de metadatos para el evento representado por el token de evento especificado, incluido el tipo declarador, los métodos add y remove para los delegados y cualquier marca y otros datos asociados.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetEventProps (  
   [in]  mdEvent       ev,  
   [out] mdTypeDef     *pClass,
   [out] LPCWSTR       szEvent,
   [in]  ULONG         cchEvent,
   [out] ULONG         *pchEvent,
   [out] DWORD         *pdwEventFlags,  
   [out] mdToken       *ptkEventType,  
   [out] mdMethodDef   *pmdAddOn,
   [out] mdMethodDef   *pmdRemoveOn,
   [out] mdMethodDef   *pmdFire,
   [out] mdMethodDef   rmdOtherMethod[],
   [in]  ULONG         cMax,  
   [out] ULONG         *pcOtherMethod  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `ev`  
 [en] El token de metadatos del evento que representa el evento para el que se obtendrán los metadatos.  
  
 `pClass`  
 [fuera] Puntero al token TypeDef que representa la clase que declara el evento.  
  
 `szEvent`  
 [fuera] El nombre del evento `ev`al que hace referencia .  
  
 `pchEvent`  
 [en] La longitud solicitada en `szEvent`caracteres anchos de .  
  
 `pdwEventFlags`  
 [fuera] La longitud devuelta `szEvent`en caracteres anchos de .  
  
 `ptkEventType`  
 [fuera] Puntero a un token de metadatos TypeRef <xref:System.Delegate> o TypeDef que representa el tipo del evento.  
  
 `pmdAddOn`  
 [fuera] Puntero al token de metadatos que representa el método que agrega controladores para el evento.  
  
 `pmdRemoveOn`  
 [fuera] Puntero al token de metadatos que representa el método que quita controladores para el evento.  
  
 `pmdFire`  
 [fuera] Puntero al token de metadatos que representa el método que provoca el evento.  
  
 `rmdOtherMethod`  
 [fuera] Matriz de punteros de token a otros métodos asociados al evento.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rmdOtherMethod`.  
  
 `pcOtherMethod`  
 [fuera] El número de `rmdOtherMethod`tokens devueltos en .  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** Incluido como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
