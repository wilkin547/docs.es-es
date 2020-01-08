---
title: Limitaciones de Async
ms.date: 12/13/2019
description: Explica las limitaciones de las API asincrónicas y algunas alternativas que puede usar en su lugar.
ms.openlocfilehash: 350237dc5c03023f60e9680e8b9c94aabb62606f
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/25/2019
ms.locfileid: "75450337"
---
# <a name="async-limitations"></a>Limitaciones de Async

SQLite no es compatible con la e/s asincrónica. Los métodos asincrónicos de ADO.NET se ejecutarán sincrónicamente en Microsoft. Data. SQLite. Evite llamarlos.

En su lugar, use [el registro de escritura previa](https://www.sqlite.org/wal.html) para mejorar el rendimiento y la simultaneidad.

[!code-csharp[](../../../../samples/snippets/standard/data/sqlite/AsyncSample/Program.cs?name=snippet_WAL)]

> [!TIP]
> El registro de escritura previa está habilitado de forma predeterminada en las bases de datos creadas mediante [Entity Framework Core](/ef/core/).
