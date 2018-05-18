---
title: Referencia de Global.json
description: Consulte el esquema del archivo global.json, que permite establecer la versión de las herramientas de .NET Core.
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.openlocfilehash: 7479774c7b9cdda233cf32d791c16e7fc6d733a8
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
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
