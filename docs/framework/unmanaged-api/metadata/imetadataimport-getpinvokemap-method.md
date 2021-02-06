---
description: 'Más información sobre: IMetaDataImport:: Getpinvokemap ((método)'
title: IMetaDataImport::GetPinvokeMap (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetPinvokeMap
helpviewer_keywords:
- IMetaDataImport::GetPinvokeMap method [.NET Framework metadata]
- GetPinvokeMap method [.NET Framework metadata]
ms.assetid: b8685c1e-b80c-4198-8eb3-748d6f48a99e
topic_type:
- apiref
ms.openlocfilehash: fcf45f4741709423aa48dcf895dfc4be276e19fe
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99649447"
---
# <a name="imetadataimportgetpinvokemap-method"></a>IMetaDataImport::GetPinvokeMap (Método)

Obtiene un token ModuleRef para representar el ensamblado de destino de una llamada PInvoke.  
  
## <a name="syntax"></a>Sintaxis  
  
```cpp  
HRESULT GetPinvokeMap (  
   [in]  mdToken       tk,  
   [out] DWORD         *pdwMappingFlags,  
   [out] LPWSTR        szImportName,  
   [in]  ULONG         cchImportName,  
   [out] ULONG         *pchImportName,  
   [out] mdModuleRef   *pmrImportDLL  
);  
```  
  
## <a name="parameters"></a>Parámetros  

 `tk`  
 de Un token de FieldDef o MethodDef para el que obtener los metadatos de asignación de PInvoke.  
  
 `pdwMappingFlags`  
 enuncia Puntero a las marcas que se usan para la asignación. Este valor es una máscara de máscara de la enumeración [CorPinvokeMap (](corpinvokemap-enumeration.md) .  
  
 `szImportName`  
 enuncia Nombre de la DLL de destino no administrada.  
  
 `cchImportName`  
 de Tamaño en caracteres anchos de `szImportName` .  
  
 `pchImportName`  
 enuncia Número de caracteres anchos devueltos en `szImportName` .  
  
 `pmrImportDLL`  
 enuncia Un puntero a un token ModuleRef que representa la biblioteca de objetos de destino no administrada.  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se incluye como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>Vea también

- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
- [IMetaDataImport2 (Interfaz)](imetadataimport2-interface.md)
