---
title: 'NETSDK1022: Se han incluido elementos duplicados.'
description: Procedimiento para resolver el mensaje de elementos duplicados en función de inclusiones predeterminadas.
author: marcpopMSFT
ms.topic: error-reference
ms.date: 10/9/2020
f1_keywords:
- NETSDK1022
ms.openlocfilehash: bc803f5316bf09c12c563f1a63b8385d1be4e9ce
ms.sourcegitcommit: bc9c63541c3dc756d48a7ce9d22b5583a18cf7fd
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 11/11/2020
ms.locfileid: "94506641"
---
# <a name="netsdk1022-duplicate-items-were-included"></a>NETSDK1022: Se han incluido elementos duplicados.

**Este artículo se aplica a:** ✔️ SDK de .NET 2.1.100 y versiones posteriores

A partir de Visual Studio 2017 y MSBuild, versión 15.3, el SDK de .NET incluye automáticamente los elementos del directorio del proyecto de forma predeterminada.  Esto incluye los destinos `Compile` y `Content`.  Esto debería limpiar en gran medida el archivo del proyecto y reducir su complejidad.

Puede revertir al comportamiento anterior si establece la propiedad correcta en "false".

Ejemplo para elementos `Compile`:

```xml
<PropertyGroup>
    <EnableDefaultCompileItems>false</EnableDefaultCompileItems>
</PropertyGroup>
```
