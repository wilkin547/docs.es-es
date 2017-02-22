---
title: Referencia de global.json | Microsoft Docs
description: Referencia de Global.json
keywords: .NET, .NET Core
author: blackdwarf
ms.author: mairaw
ms.date: 11/02/2016
ms.topic: article
ms.prod: .net-core
ms.technology: dotnet-cli
ms.devlang: dotnet
ms.assetid: 96102f96-d403-4385-8ef6-5d80e406eb0c
translationtype: Human Translation
ms.sourcegitcommit: 796df1549a7553aa93158598d62338c02d4df73e
ms.openlocfilehash: b814bfc79c2fcd0fd15b9494c18c6d0443a70fb1

---

# <a name="globaljson-reference-net-core-tools-rc4"></a>Referencia de global.json (.NET Core Tools RC4)

> [!WARNING]
> Este tema se aplica a .NET Core Tools RC4. Para la versión .NET Core Tools Preview 2, consulte el tema [Referencia de global.json](../../tools/global-json.md).

El archivo global.json sigue estando presente en la línea de comandos de .NET Core RC4. Sin embargo, su propósito principal no es definir metadatos de solución como en versiones anteriores, sino para permitir la selección de la versión de la CLI que se usa mediante la propiedad `sdk`. 

Esta referencia refleja el hecho anterior. 

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


<!--HONumber=Feb17_HO2-->


