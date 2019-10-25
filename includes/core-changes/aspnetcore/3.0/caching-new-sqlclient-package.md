---
ms.openlocfilehash: 32c7f4e9e4736145f9275b74f34c04404e7c770a
ms.sourcegitcommit: 2e95559d957a1a942e490c5fd916df04b39d73a9
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 10/16/2019
ms.locfileid: "72394049"
---
### <a name="caching-microsoftextensionscachingsqlserver-uses-new-sqlclient-package"></a>Almacenamiento en caché: Microsoft.Extensions.Caching.SqlServer usa el paquete nuevo SqlClient

El paquete `Microsoft.Extensions.Caching.SqlServer` usará el paquete nuevo `Microsoft.Data.SqlClient` en lugar del `System.Data.SqlClient`. Este cambio podría producir pequeños cambios en el comportamiento. Para obtener más información, vea [Introducción al nuevo Microsoft.Data.SqlClient](https://devblogs.microsoft.com/dotnet/introducing-the-new-microsoftdatasqlclient/).

#### <a name="version-introduced"></a>Versión introducida

3.0

#### <a name="old-behavior"></a>Comportamiento anterior

El paquete `Microsoft.Extensions.Caching.SqlServer` usaba el paquete `System.Data.SqlClient`.

#### <a name="new-behavior"></a>Comportamiento nuevo

`Microsoft.Extensions.Caching.SqlServer` ahora usa el paquete `Microsoft.Data.SqlClient`.

#### <a name="reason-for-change"></a>Motivo del cambio

`Microsoft.Data.SqlClient` es un nuevo paquete que se ha creado a partir de `System.Data.SqlClient`. A partir de ahora, aquí es donde se realizará todo el trabajo de las nuevas características.

#### <a name="recommended-action"></a>Acción recomendada

Los clientes no deben preocuparse por este cambio importante, a menos que usaran los tipos que devolvía el paquete `Microsoft.Extensions.Caching.SqlServer` y los convirtieran en tipos de `System.Data.SqlClient`. Por ejemplo, si algún usuario estuviera convirtiendo un elemento `DbConnection` al [tipo de SqlConnection anterior](xref:System.Data.SqlClient.SqlConnection), tendría que cambiar la conversión al nuevo tipo de `Microsoft.Data.SqlClient.SqlConnection`. 

#### <a name="category"></a>Categoría

ASP.NET Core

#### <a name="affected-apis"></a>API afectadas

None

<!-- 

#### Affected APIs

Not detectable via API analysis

-->
