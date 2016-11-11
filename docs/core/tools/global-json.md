---
title: Referencia de Global.json | .NET Core
description: Referencia de Global.json
keywords: .NET, .NET Core
author: aL3891
ms.author: mairaw
manager: wpickett
ms.date: 11/02/2016
ms.topic: article
ms.prod: .net-core
ms.technology: .net-core-technologies
ms.devlang: dotnet
ms.assetid: e1ac9659-425f-4486-a376-c12ca942ead8
translationtype: Human Translation
ms.sourcegitcommit: 6f3a46284bd5820520739577919fa202f5b784d7
ms.openlocfilehash: 2353a22ea41c3fbf5700ba40da5cdb89b5bf2872

---

# <a name="globaljson-reference"></a>Referencia de Global.json

El archivo global.json se utiliza en los proyectos de .NET Core para definir los metadatos de la solución. Este archivo se usa cuando el comando [dotnet-restore](dotnet-restore.md) se invoca para restaurar las dependencias de un proyecto de .NET Core.
En este tema de referencia, verá la lista de las propiedades que puede definir en el archivo global.json.

## <a name="projects"></a>proyectos
Tipo: String[]

Especifica en qué carpetas el sistema de compilación debe buscar proyectos al resolver dependencias. El sistema de compilación solo buscará carpetas secundarias de nivel superior.

Por ejemplo:

```json
{
    "projects": [ "src", "test" ]
}
```

## <a name="packages"></a>paquetes
Tipo: string

Ubicación para almacenar paquetes.

Por ejemplo:
```json
{
    "packages": "packages-dir"
}
```

## <a name="sdk"></a>sdk
Tipo: objeto

Especifica información acerca del SDK.

### <a name="version"></a>version
Tipo: string

Versión del SDK para usar.

Por ejemplo:

```json
{
    "sdk": {
        "version": "1.0.0-preview2-003121"
    }
}
```



<!--HONumber=Nov16_HO1-->


