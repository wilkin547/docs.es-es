---
description: 'Más información sobre: clase AssemblyAttributesGoHere'
title: Clase AssemblyAttributesGoHere (System. Runtime. CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHere
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHere
helpviewer_keywords:
- AssemblyAttributesGoHere type
- Alink API, AssemblyAttributesGoHere type
ms.assetid: 7b26fcb6-94f4-4f09-933e-b33efe451f4f
topic_type:
- apiref
ms.openlocfilehash: b95ff377f7fa0ffc85136dd69eb4a32121a50dc2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638592"
---
# <a name="assemblyattributesgohere-class"></a>Clase AssemblyAttributesGoHere

ALink lo utiliza como marcador de posición para almacenar información acerca de los atributos personalizados.

## <a name="syntax"></a>Sintaxis

```csharp
internal sealed class AssemblyAttributesGoHere
```

## <a name="remarks"></a>Observaciones

Las referencias a este tipo se pueden incrustar en archivos .netmodules cuyos orígenes contengan atributos personalizados de ensamblado. Cuando se genera un manifiesto de ensamblado de uno o más .netmodules que contienen referencias a estos tipos, ALink utiliza la información adjunta a estas referencias para emitir atributos personalizados reales. Como tal, nunca se crea una instancia de este tipo y las referencias a él se utilizan únicamente como parte del proceso de compilación, no sirven para ningún propósito en el ensamblado final.

Las referencias a este tipo indican atributos personalizados que no están relacionados con la seguridad y que no tienen diversos usos.

Estos tipos se marcan como "Internal" dentro del .NET Framework y se encuentran en el <xref:System.Runtime.CompilerServices> espacio de nombres.

## <a name="requirements"></a>Requisitos

mscorlib.dll

## <a name="see-also"></a>Vea también

- [AssemblyAttributesGoHereM](assemblyattributesgoherem.md)
- [AssemblyAttributesGoHereS](assemblyattributesgoheres.md)
- [AssemblyAttributesGoHereSM](assemblyattributesgoheresm.md)
