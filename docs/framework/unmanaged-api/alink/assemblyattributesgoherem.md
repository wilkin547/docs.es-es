---
description: 'Más información sobre: clase AssemblyAttributesGoHereM'
title: Clase AssemblyAttributesGoHereM (System. Runtime. CompilerServices)
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereM
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereM
helpviewer_keywords:
- AssemblyAttributesGoHereM type
- Alink API, AssemblyAttributesGoHereM type
ms.assetid: caaa8ba9-b4bb-4dd6-934d-57e436b2f3e5
topic_type:
- apiref
ms.openlocfilehash: 9afa72e5adbd539acaf8dfe45b446a61862df49e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99638579"
---
# <a name="assemblyattributesgoherem-class"></a>Clase AssemblyAttributesGoHereM

ALink lo utiliza como marcador de posición para almacenar información acerca de los atributos personalizados.

## <a name="syntax"></a>Sintaxis

```csharp
internal sealed class AssemblyAttributesGoHereM
```

## <a name="remarks"></a>Observaciones

Las referencias a este tipo se pueden incrustar en archivos .netmodules cuyos orígenes contengan atributos personalizados de ensamblado. Cuando se genera un manifiesto de ensamblado de uno o más .netmodules que contienen referencias a estos tipos, ALink utiliza la información adjunta a estas referencias para emitir atributos personalizados reales. Como tal, nunca se crea una instancia de este tipo y las referencias a él se utilizan únicamente como parte del proceso de compilación, no sirven para ningún propósito en el ensamblado final.

Las referencias a este tipo indican atributos personalizados que no están relacionados con la seguridad, pero que tienen diversos usos.

Estos tipos se marcan como "Internal" dentro del .NET Framework y se encuentran en el <xref:System.Runtime.CompilerServices> espacio de nombres.

## <a name="requirements"></a>Requisitos

mscorlib.dll

## <a name="see-also"></a>Vea también

- [AssemblyAttributesGoHere](assemblyattributesgohere.md)
- [AssemblyAttributesGoHereS](assemblyattributesgoheres.md)
- [AssemblyAttributesGoHereSM](assemblyattributesgoheresm.md)
