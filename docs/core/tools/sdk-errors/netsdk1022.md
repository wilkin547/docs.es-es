---
title: 'NETSDK1022: Se han incluido elementos duplicados.'
description: Procedimiento para resolver el mensaje de elementos duplicados en función de inclusiones predeterminadas.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1022
ms.openlocfilehash: c2bdbbb5503e5e4f6e6826f95f5a2cb08c908ceb
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/24/2020
ms.locfileid: "95717880"
---
# <a name="netsdk1022-duplicate-items-were-included"></a>NETSDK1022: Se han incluido elementos duplicados.

**Este artículo se aplica a: ✔️** SDK de .NET Core 2.1.100 y versiones posteriores

A partir de Visual Studio 2017 y MSBuild, versión 15.3, el SDK de .NET incluye automáticamente los elementos del directorio del proyecto de forma predeterminada.  Esto incluye los destinos `Compile` y `Content`.  Esto debería limpiar en gran medida el archivo del proyecto y reducir su complejidad.

Puede revertir al comportamiento anterior si establece la propiedad correcta en "false".

Ejemplo para elementos `Compile`:

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
