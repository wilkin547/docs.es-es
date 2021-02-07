---
description: 'Más información sobre: IMetaDataEmit:: Mergeend ((método)'
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
ms.openlocfilehash: aac48b9bafb60cee4e3d73232d9f9c00cca7f796
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99745884"
---
# <a name="imetadataemitmergeend-method"></a>IMetaDataEmit::MergeEnd (Método)

Combina en el ámbito actual todos los ámbitos de metadatos especificados por una o varias llamadas anteriores a [IMetaDataEmit:: Merge](imetadataemit-merge-method.md).

## <a name="syntax"></a>Sintaxis

```cppcpp
HRESULT MergeEnd ();
```

## <a name="parameters"></a>Parámetros

Este método no toma ningún parámetro.

## <a name="remarks"></a>Observaciones

Esta rutina desencadena la combinación real de metadatos, de todos los ámbitos de importación especificados por las llamadas anteriores a `IMetaDataEmit::Merge` , en el ámbito de salida actual.

Las condiciones especiales siguientes se aplican a la combinación:

- Un identificador de versión de módulo (MVID) nunca se importa porque es único en los metadatos del ámbito de importación.

- No se sobrescriben las propiedades de todo el módulo.

  Si ya se han establecido las propiedades del módulo para el ámbito actual, no se importa ninguna propiedad del módulo. Sin embargo, si no se han establecido las propiedades del módulo en el ámbito actual, se importan solo una vez, cuando se encuentran por primera vez. Si las propiedades del módulo se encuentran de nuevo, son duplicados. Si se comparan los valores de todas las propiedades del módulo (excepto MVID) y no se encuentra ningún duplicado, se produce un error.

- En las definiciones de tipo ( `TypeDef` ), no se combina ningún duplicado en el ámbito actual. `TypeDef`los objetos se comprueban en busca de duplicados en cada número de versión del GUID del *nombre de objeto completo*  +    +  . Si hay una coincidencia en el nombre o el GUID, y cualquiera de los otros dos elementos es diferente, se genera un error. De lo contrario, si los tres elementos coinciden, `MergeEnd` realiza una comprobación de cursor para asegurarse de que las entradas son realmente duplicados; si no es así, se produce un error. Esta comprobación de cursor busca:

  - Las mismas declaraciones de miembros, que se producen en el mismo orden. Los miembros que se marcan como `mdPrivateScope` (vea la enumeración [cormethodattr (](cormethodattr-enumeration.md) ) no se incluyen en esta comprobación; se combinan de forma especial.

  - El mismo diseño de clase.

  Esto significa que un `TypeDef` objeto siempre debe estar definido de forma completa y coherente en cada ámbito de metadatos en el que se declara; si sus implementaciones de miembro (para una clase) se distribuyen entre varias unidades de compilación, se supone que la definición completa está presente en todos los ámbitos y no incremental en cada ámbito. Por ejemplo, si los nombres de parámetro son relevantes para el contrato, deben emitirse de la misma manera en todos los ámbitos; Si no son relevantes, no se deben emitir en metadatos.

  La excepción es que un `TypeDef` objeto puede tener miembros incrementales marcados como `mdPrivateScope` . Al encontrarlos, `MergeEnd` los agrega incrementalmente al ámbito actual sin tener en cuenta los duplicados. Dado que el compilador entiende el ámbito privado, el compilador debe ser responsable de aplicar las reglas.

- Las direcciones virtuales relativas (RVA) no se importan ni se combinan; se espera que el compilador vuelva a emitir esta información.

- Los atributos personalizados solo se combinan cuando se combina el elemento al que están adjuntos. Por ejemplo, los atributos personalizados asociados a una clase se combinan cuando la clase se encuentra por primera vez. Si los atributos personalizados están asociados a un objeto `TypeDef` o `MemberDef` que es específico de la unidad de compilación (por ejemplo, la marca de tiempo de una compilación de miembro), no se combinan y depende del compilador quitar o actualizar dichos metadatos.

## <a name="requirements"></a>Requisitos

**Plataformas:** Vea [Requisitos de sistema](../../get-started/system-requirements.md).

**Encabezado:** Cor. h

**Biblioteca:** Se usa como un recurso en MSCorEE.dll

**.NET Framework versiones:**[!INCLUDE[net_current_v11plus](../../../../includes/net-current-v11plus-md.md)]

## <a name="see-also"></a>Vea también

- [IMetaDataEmit (Interfaz)](imetadataemit-interface.md)
- [IMetaDataEmit2 (Interfaz)](imetadataemit2-interface.md)
