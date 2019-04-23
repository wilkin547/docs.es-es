---
title: IMetaDataImport::GetParamProps (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetParamProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetParamProps
helpviewer_keywords:
- IMetaDataImport::GetParamProps method [.NET Framework metadata]
- GetParamProps method [.NET Framework metadata]
ms.assetid: 4d5e5f00-bcab-4f41-b191-176511a186a7
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 05ac8efed8c0a905d2cfad433348a99fe578eeae
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59153184"
---
# <a name="imetadataimportgetparamprops-method"></a>IMetaDataImport::GetParamProps (Método)
Obtiene los valores de los metadatos del parámetro al que hace referencia el token de ParamDef especificado.  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT GetParamProps (  
   [in]  mdParamDef      tk,  
   [out] mdMethodDef     *pmd,  
   [out] ULONG           *pulSequence,  
   [out] LPWSTR          szName,  
   [in]  ULONG           cchName,  
   [out] ULONG           *pchName,  
   [out] DWORD           *pdwAttr,  
   [out] DWORD           *pdwCPlusTypeFlag,  
   [out] UVCP_CONSTANT   *ppValue,  
   [out] ULONG           *pcchValue  
);  
```  
  
## <a name="parameters"></a>Parámetros  
 `tk`  
 [in] Un token de ParamDef que representa el parámetro para devolver los metadatos.  
  
 `pmd`  
 [out] Un puntero a un token de MethodDef que representa el método que toma el parámetro.  
  
 `pulSequence`  
 [out] La posición ordinal del parámetro en la lista de argumentos de método.  
  
 `szName`  
 [out] Un búfer para almacenar el nombre del parámetro.  
  
 `cchName`  
 [in] El tamaño solicitado en caracteres anchos de `szName`.  
  
 `pchName`  
 [out] El tamaño devuelto en caracteres anchos de `szName`.  
  
 `pdwAttr`  
 [out] Un puntero a cualquier indicador de atributo asociado al parámetro. Se trata de una máscara de bits de `CorParamAttr` valores.  
  
 `pdwCPlusTypeFlag`  
 [out] Un puntero a una marca que especifica que el parámetro es un <xref:System.ValueType>.  
  
 `ppValue`  
 [out] Un puntero a una cadena constante devuelta por el parámetro.  
  
 `pcchValue`  
 [out] El tamaño de `ppValue` en caracteres anchos, o cero si `ppValue` no contiene una cadena.  
  
## <a name="remarks"></a>Comentarios

Los valores de secuencia en `pulSequence` comienzan por 1 para los parámetros. Un valor devuelto tiene un número de secuencia de 0.

## <a name="requirements"></a>Requisitos  
 **Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado**: Cor.h  
  
 **Biblioteca:** Incluye como recurso en MsCorEE.dll  
  
 **Versiones de .NET Framework:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)
- [IMetaDataImport2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)
