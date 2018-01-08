---
title: Referencia de Global.json
description: "Consulte el esquema del archivo global.json, que permite establecer la versión de las herramientas de .NET Core."
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 04/05/2017
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 96102f96-d403-4385-8ef6-5d80e406eb0c
ms.workload: dotnetcore
ms.openlocfilehash: c7e64995ed00a6b2df1b7e1dfa43c6bea5cf4535
ms.sourcegitcommit: e7f04439d78909229506b56935a1105a4149ff3d
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 12/23/2017
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
