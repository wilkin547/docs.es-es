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
ms.openlocfilehash: 6e512b7cd8869c6ede1472bbc5b6ec4c428b40ef
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 07/10/2019
ms.locfileid: "67757647"
---
# <a name="imetadataemitmergeend-method"></a>IMetaDataEmit::MergeEnd (Método)

Combina en el actual ámbito de todos los ámbitos de los metadatos especificados por una o varias llamadas anteriores al [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-merge-method.md).

## <a name="syntax"></a>Sintaxis

```cppcpp
HRESULT MergeEnd ();
```

## <a name="parameters"></a>Parámetros

Este método no toma ningún parámetro.

## <a name="remarks"></a>Comentarios

Esta rutina desencadena la combinación real de los metadatos, de todos los ámbitos especificados utilizando delante de las llamadas a de importación `IMetaDataEmit::Merge`, en el ámbito de salida actual.

Se aplican las siguientes condiciones especiales para la fusión mediante combinación:

- Un identificador de versión de módulo (MVID) nunca se importa, porque es único para los metadatos en el ámbito de importación.

- No hay propiedades de todo el módulo existentes se sobrescriben.

  Si ya se han establecido propiedades del módulo para el ámbito actual, no hay propiedades del módulo se importan. Sin embargo, si no se han establecido las propiedades de módulo en el ámbito actual, se importan solo una vez, cuando se encuentran en primer lugar. Si se vuelven a encontrar las propiedades de módulo, son duplicados. Si se comparan los valores de todas las propiedades de módulo (excepto el MVID) y no se encuentran duplicados, se produce un error.

- Para obtener definiciones de tipo (`TypeDef`), no hay duplicados se combinan en el ámbito actual. `TypeDef` se comprueban los objetos duplicados en cada *nombre de objeto completo* + *GUID* + *número de versión*. Si hay una coincidencia en el nombre o GUID y cualquiera de los otros dos elementos es diferente, se produce un error. En caso contrario, si coincide con los tres elementos, `MergeEnd` realiza una comprobación rápida para asegurarse de que las entradas son en realidad duplicados; en caso contrario, se produce un error. Esta comprobación superficial busca:

  - Las declaraciones de miembro mismo, que se producen en el mismo orden. Los miembros que se marcan como `mdPrivateScope` (consulte la [CorMethodAttr](../../../../docs/framework/unmanaged-api/metadata/cormethodattr-enumeration.md) enumeración) no se incluyen en esta comprobación; se combinan de manera especial.

  - El mismo diseño de clase.

  Esto significa que un `TypeDef` objeto debe siempre por completo y coherente definirse en cada ámbito de metadatos donde se declara; si sus implementaciones de miembros (para una clase) se reparten entre varias unidades de compilación, la definición completa se supone que presente en cada ámbito y no es incremental para cada ámbito. Por ejemplo, si los nombres de parámetro son relevantes para el contrato, se debe emitir la misma manera en cada ámbito; Si no son relevantes, no se emiten en metadatos.

  La excepción es que un `TypeDef` objeto puede tener miembros incrementales marcados como `mdPrivateScope`. Al encontrar estos, `MergeEnd` agrega incrementalmente el ámbito actual sin tener en cuenta los duplicados. Dado que el compilador reconoce el ámbito privado, el compilador debe ser responsable de aplicar las reglas.

- No se importan o se combinan; direcciones virtuales relativas (RVA) el compilador se espera volver a emitir esta información.

- Se combinan los atributos personalizados solo cuando se combina el elemento al que están conectados. Por ejemplo, se combinan los atributos personalizados asociados a una clase cuando la clase se encuentra en primer lugar. Si los atributos personalizados que están asociados con un `TypeDef` o `MemberDef` específica de la unidad de compilación (por ejemplo, la marca de tiempo de compilación de un miembro), no se combinan y se deja al compilador que quitar o actualizar estos metadatos.

## <a name="requirements"></a>Requisitos

**Plataformas:** Consulte [Requisitos del sistema](../../../../docs/framework/get-started/system-requirements.md).

**Encabezado**: Cor.h

**Biblioteca:** Usar como un recurso en MSCorEE.dll

**Versiones de .NET Framework:** [!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]

## <a name="see-also"></a>Vea también

- [IMetaDataEmit (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md)
- [IMetaDataEmit2 (interfaz)](../../../../docs/framework/unmanaged-api/metadata/imetadataemit2-interface.md)
