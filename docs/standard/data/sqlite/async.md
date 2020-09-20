---
title: Limitaciones de Async
ms.date: 09/04/2020
description: Se explican las limitaciones de las API asincrónicas y algunas alternativas que puede usar en su lugar.
ms.openlocfilehash: 8b14fcfeb12d331d8d43ca6d77332007a12ae5dc
ms.sourcegitcommit: 0c3ce6d2e7586d925a30f231f32046b7b3934acb
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/08/2020
ms.locfileid: "89516000"
---
# <a name="async-limitations"></a>Limitaciones de Async

SQLite no es compatible con la E/S asincrónica. Los métodos asincrónicos de ADO.NET se ejecutarán de forma sincrónica en Microsoft.Data.SQLite. Evite llamarlos.

En su lugar, use una [caché compartida](connection-strings.md#cache) y el [registro de escritura anticipada](https://www.sqlite.org/wal.html) para mejorar el rendimiento y la simultaneidad.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> El registro de escritura anticipada está habilitado de forma predeterminada en las bases de datos creadas mediante [Entity Framework Core](/ef/core/).
