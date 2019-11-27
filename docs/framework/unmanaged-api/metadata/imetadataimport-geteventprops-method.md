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
ms.openlocfilehash: 18fe0c834506d0ac4cd15fd7af4c4f15904b0f81
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/23/2019
ms.locfileid: "74437575"
---
# <a name="imetadataimportgeteventprops-method"></a>IMetaDataImport::GetEventProps (Método)
Obtiene información de metadatos para el evento representado por el token de evento especificado, incluido el tipo declarativo, los métodos Add y Remove para los delegados, y cualquier marcador y otros datos asociados.  
  
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
 de Token de metadatos de evento que representa el evento para el que se van a obtener los metadatos.  
  
 `pClass`  
 enuncia Un puntero al token de TypeDef que representa la clase que declara el evento.  
  
 `szEvent`  
 enuncia Nombre del evento al que hace referencia `ev`.  
  
 `pchEvent`  
 de La longitud solicitada en caracteres anchos de `szEvent`.  
  
 `pdwEventFlags`  
 enuncia La longitud devuelta en caracteres anchos de `szEvent`.  
  
 `ptkEventType`  
 enuncia Un puntero a un símbolo (token) de metadatos de TypeRef o TypeDef que representa el tipo de <xref:System.Delegate> del evento.  
  
 `pmdAddOn`  
 enuncia Un puntero al token de metadatos que representa el método que agrega controladores para el evento.  
  
 `pmdRemoveOn`  
 enuncia Un puntero al token de metadatos que representa el método que quita los controladores para el evento.  
  
 `pmdFire`  
 enuncia Un puntero al token de metadatos que representa el método que genera el evento.  
  
 `rmdOtherMethod`  
 enuncia Matriz de punteros de token a otros métodos asociados al evento.  
  
 `cMax`  
 [in] Tamaño máximo de la matriz `rmdOtherMethod`.  
  
 `pcOtherMethod`  
 enuncia Número de tokens devueltos en `rmdOtherMethod`.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** Vea [Requisitos de sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como recurso en MsCorEE. dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
