---
ms.openlocfilehash: 687118157020ede200f97a0125c4740a06bf4b5e
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620614"
---
### <a name="different-exception-handling-for-objectcontextcreatedatabase-and-dbproviderservicescreatedatabase-methods"></a>Control de excepciones diferente para los métodos ObjectContext.CreateDatabase y DbProviderServices.CreateDatabase

#### <a name="details"></a>Detalles

A partir de .NET Framework 4.5, si se produce un error en la creación de la base de datos, los métodos <code>CreateDatabase</code> intentarán eliminar la base de datos vacía. Si esa operación se realiza correctamente, se propagará la excepción <xref:System.Data.SqlClient.SqlException?displayProperty=fullName> original (en lugar de la excepción <xref:System.InvalidOperationException?displayProperty=fullName>, que siempre se iniciaba en .NET Framework 4.0).

#### <a name="suggestion"></a>Sugerencia

Cuando se detecta una excepción <xref:System.InvalidOperationException?displayProperty=fullName> al ejecutar <xref:System.Data.Objects.ObjectContext.CreateDatabase> o <xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)>, ahora también se deben detectar las excepciones SQLExceptions.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Data.Objects.ObjectContext.CreateDatabase?displayProperty=nameWithType></li><li><xref:System.Data.Common.DbProviderServices.CreateDatabase(System.Data.Common.DbConnection,System.Nullable{System.Int32},System.Data.Metadata.Edm.StoreItemCollection)?displayProperty=nameWithType></li></ul>|
