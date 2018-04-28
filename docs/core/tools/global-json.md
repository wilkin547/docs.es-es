---
title: Referencia de Global.json
description: Consulte el esquema del archivo global.json, que permite establecer la versión de las herramientas de .NET Core.
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.topic: conceptual
ms.prod: dotnet-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.workload:
- dotnetcore
ms.openlocfilehash: ac53a899e76c99527f2670d0a6bed3f8cc6ce31f
ms.sourcegitcommit: 03ee570f6f528a7d23a4221dcb26a9498edbdf8c
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/28/2018
---
# <a name="globaljson-reference"></a>Referencia de Global.json

El archivo *global.json* permite la selección de la versión de herramientas de .NET Core que se está usando mediante la propiedad `sdk`.

Las herramientas de la CLI de .NET Core buscan este archivo en el directorio de trabajo actual (que no es necesariamente el mismo que el directorio del proyecto) o uno de sus directorios principales.

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
