---
ms.openlocfilehash: e65ba0edb132f5cded244a69d58e43ffea76a039
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 09/15/2020
ms.locfileid: "90606896"
---
### <a name="sqlconnection-can-no-longer-connect-to-sql-server-1997-or-databases-using-the-via-adapter"></a>SqlConnection ya no se puede conectar a SQL Server 1997 o a bases de datos mediante el adaptador VIA

#### <a name="details"></a>Detalles

Ya no se admiten las conexiones a las bases de datos de SQL Server mediante el [protocolo Adaptador de interfaz virtual (VIA)](/previous-versions/sql/sql-server-2008-r2/ms191229(v=sql.105)). El protocolo que se usa para conectarse a una base de datos de SQL Server es visible en la cadena de conexión. Una conexión de VIA contendrá via:&lt;nombre_de_servidor&gt;. Si esta aplicación se conecta a SQL a través de un protocolo distinto de VIA (tcp: o np: por ejemplo), no se encontrará ningún cambio importante. Además, ya no se admiten las conexiones a SQL Server 7 (1997).

#### <a name="suggestion"></a>Sugerencia

El protocolo VIA está en desuso, por lo que se debe usar un protocolo alternativo para conectarse a las bases de datos SQL. El protocolo que más se usa es TCP/IP. Para más información sobre cómo conectarse a través de TCP/IP, consulte el artículo sobre cómo [habilitar el protocolo TCP/IP para una instancia de base de datos](/previous-versions/visualstudio/visual-studio-2008/bb909712(v=vs.90)). Si solo se tiene acceso a la base de datos desde dentro de una intranet, el protocolo de canalizaciones compartidas puede proporcionar un mejor rendimiento si la red es lenta.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|

#### <a name="affected-apis"></a>API afectadas

- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String)>
- <xref:System.Data.SqlClient.SqlConnection.%23ctor(System.String,System.Data.SqlClient.SqlCredential)>

<!--

#### Affected APIs

- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String)`
- `M:System.Data.SqlClient.SqlConnection.#ctor(System.String,System.Data.SqlClient.SqlCredential)`

-->
