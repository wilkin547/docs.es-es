---
title: IMetaDataEmit::MergeEnd (Método)
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.MergeEnd
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::MergeEnd
helpviewer_keywords:
- MergeEnd method [.NET Framework metadata]
- IMetaDataEmit::MergeEnd method [.NET Framework metadata]
ms.assetid: 2d64315a-1af1-4c60-aedf-f8a781914aea
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b794a62a0ac0d253f1431be29b43101816dc7233
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="imetadataemitmergeend-method"></a>IMetaDataEmit::MergeEnd (Método)
Definir el ámbito de mezclas en actual todos los ámbitos de metadatos especificados por una o más llamadas anteriores a [IMetaDataEmit:: Merge](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).  
  
## <a name="syntax"></a>Sintaxis  
  
```  
HRESULT MergeEnd ();  
```  
  
#### <a name="parameters"></a>Parámetros  
 Este método no toma ningún parámetro.  
  
## <a name="remarks"></a>Comentarios  
 Esta rutina desencadena la verdadera combinación de metadatos, de todos los ámbitos especificados por delante de las llamadas a de importación `IMetaDataEmit::Merge`, en el ámbito de salida actual.  
  
 Las siguientes condiciones especiales se aplican a la combinación:  
  
-   Nunca se importa un identificador de versión de módulo (MVID), porque es único para los metadatos en el ámbito de importación.  
  
-   No todo el módulo de las propiedades existentes se sobrescriben.  
  
     Si ya se han establecido las propiedades del módulo para el ámbito actual, no se importa ninguna propiedad de módulo. Sin embargo, si las propiedades del módulo no se han configurado en el ámbito actual, se importan solo una vez, cuando se encuentran en primer lugar. Si se vuelven a encontrar esas propiedades de módulo, son duplicados. Si se comparan los valores de todas las propiedades de módulo (excepto el MVID) y no se encuentran duplicados, se produce un error.  
  
-   Para obtener definiciones de tipo (`TypeDef`), duplicados no se combinan en el ámbito actual. `TypeDef` se comprueban los objetos duplicados en todas *nombre de objeto completo* + *GUID* + *número de versión*. Si hay una coincidencia de nombre o GUID y cualquiera de los otros dos elementos es diferente, se produce un error. En caso contrario, si coincide con los tres elementos, `MergeEnd` realiza una comprobación rápida para asegurarse de que las entradas son en realidad duplicados; en caso contrario, se produce un error. Esta comprobación superficial busca:  
  
    -   Las declaraciones de miembro mismo, que se producen en el mismo orden. Los miembros que estén marcados como `mdPrivateScope` (consulte la [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeración) no se incluyen en esta comprobación; se combinan de manera especial.  
  
    -   El mismo diseño de clase.  
  
     Esto significa que un `TypeDef` objeto debe siempre completa y coherente definirse en cada ámbito de metadatos donde se declara; si sus implementaciones de miembros (para una clase) se reparten entre varias unidades de compilación, la definición completa se supone que presentes en cada ámbito y no de forma incremental a cada ámbito. Por ejemplo, si los nombres de parámetro son relevantes para el contrato, se debe emitir la misma manera en cada ámbito; Si no son relevantes, no se emite en metadatos.  
  
     La excepción es que un `TypeDef` objeto puede tener miembros incrementales marcados como `mdPrivateScope`. Al encontrar estos, `MergeEnd` agrega incrementalmente al ámbito actual sin tener en cuenta para los duplicados. Dado que el compilador reconoce el ámbito privado, el compilador debe ser responsable de aplicar las reglas.  
  
-   Direcciones virtuales relativas (RVA) no se importan o se combinan; el compilador debe volver a emitir esta información.  
  
-   Atributos personalizados se combinan solo cuando se combina el elemento al que se adjunta. Por ejemplo, se combinan los atributos personalizados asociados a una clase cuando la clase aparece por primera vez. Si los atributos personalizados están asociados con un `TypeDef` o `MemberDef` que es específico de la unidad de compilación (por ejemplo, la marca de tiempo de una compilación de miembro), no se combinan y se deja al compilador que quitar o actualizar tales metadatos.  
  
## <a name="requirements"></a>Requisitos  
 **Plataformas:** vea [requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).  
  
 **Encabezado:** Cor.h  
  
 **Biblioteca:** usada como recurso en MSCorEE.dll  
  
 **Versiones de .NET framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]  
  
## <a name="see-also"></a>Vea también  
 [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)  
 [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
