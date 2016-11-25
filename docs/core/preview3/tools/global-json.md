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
ms.sourcegitcommit: 1a84c694945fe0c77468eb77274ab46618bccae6
ms.openlocfilehash: 281f1b717a0e220e533078e973711977617a1401

---

# <a name="globaljson-reference"></a>Referencia de Global.json

El archivo global.json sigue estando presente en la línea de comandos de .NET Core Preview 3. Sin embargo, su propósito principal no es definir metadatos de solución como en versiones anteriores, sino para permitir la selección de la versión de la CLI que se usa mediante la propiedad `sdk`. 

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



<!--HONumber=Nov16_HO3-->


