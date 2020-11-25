---
title: IMetaDataImport2 (Interfaz)
ms.date: 03/30/2017
api_name:
- IMetaDataImport2
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport2
helpviewer_keywords:
- IMetaDataImport2 interface [.NET Framework metadata]
ms.assetid: d39b2b87-ba53-4771-ae53-952a68452511
topic_type:
- apiref
ms.openlocfilehash: a845ecfde6583d625d2a8f165443344ff9e40d05
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95702557"
---
# <a name="imetadataimport2-interface"></a>IMetaDataImport2 (Interfaz)

Extiende la interfaz [IMetaDataImport](imetadataimport-interface.md) para proporcionar la capacidad de trabajar con tipos genéricos.  
  
## <a name="methods"></a>Métodos  
  
|Método|Descripción|  
|------------|-----------------|  
|[Método EnumGenericParamConstraints](imetadataimport2-enumgenericparamconstraints-method.md)|Obtiene un enumerador para una matriz de restricciones de parámetros genéricos asociada al parámetro genérico representado por el token especificado.|  
|[Método EnumGenericParams](imetadataimport2-enumgenericparams-method.md)|Obtiene un enumerador para una matriz de tokens de parámetro genéricos asociados al token de TypeDef o MethodDef especificado.|  
|[Método EnumMethodSpecs](imetadataimport2-enummethodspecs-method.md)|Obtiene un enumerador para una matriz de tokens MethodSpec asociados al token MethodDef o MemberRef especificado.|  
|[Método GetGenericParamConstraintProps](imetadataimport2-getgenericparamconstraintprops-method.md)|Obtiene los metadatos asociados a la restricción de parámetro genérico que representa el token de restricción especificado.|  
|[Método GetGenericParamProps](imetadataimport2-getgenericparamprops-method.md)|Obtiene los metadatos asociados al parámetro genérico representado por el token especificado.|  
|[Método GetMethodSpecProps](imetadataimport2-getmethodspecprops-method.md)|Obtiene la firma de metadatos del método al que hace referencia el token MethodSpec especificado.|  
|[Método GetPEKind](imetadataimport2-getpekind-method.md)|Obtiene un valor que identifica la naturaleza del código en un archivo portable ejecutable (PE), normalmente un archivo DLL o EXE, definido en el ámbito de metadatos actual.|  
|[Método GetVersionString](imetadataimport2-getversionstring-method.md)|Obtiene el número de versión del motor en tiempo de ejecución que se usó para compilar el ensamblado.|  
  
## <a name="requirements"></a>Requisitos  

 **Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).  
  
 **Encabezado:** Cor. h  
  
 **Biblioteca:** Se usa como un recurso en MsCorEE.dll  
  
 **.NET Framework versiones:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a>Consulte también

- <xref:System.Reflection.PortableExecutableKinds>
- [Interfaces de metadatos](metadata-interfaces.md)
- [IMetaDataImport (Interfaz)](imetadataimport-interface.md)
