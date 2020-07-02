---
ms.openlocfilehash: a1db9916c69c5974191eb6108fb54a0d9ff060d2
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85622134"
---
### <a name="sqlconnectionopen-fails-on-windows-7-with-non-ifs-winsock-bsp-or-lsp-present"></a>Se produce un error de SqlConnection.Open en Windows 7 con presencia de un BSP o LSP de Winsock distinto de IFS

#### <a name="details"></a>Detalles

Se produce un error de <xref:System.Data.SqlClient.SqlConnection.Open> y <xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)> en .NET Framework 4.5 si se ejecutan en un equipo Windows 7 con un Winsock BSP o LSP que no sea IFS en el equipo. Para determinar si está instalado un LSP o BSP distinto de IFS, use el comando <code>netsh WinSock Show Catalog</code> y examine todos los elementos <code>Winsock Catalog Provider Entry</code> que se devuelven. Si el valor Service Flags tiene establecido el bit <code>0x20000</code>, el proveedor usa controladores IFS y funcionará correctamente. Si el bit <code>0x20000</code> está claro (no establecido), se trata de un BSP o LSP distinto de IFS.

#### <a name="suggestion"></a>Sugerencia

Este error se corrigió en .NET Framework 4.5.2, por lo que se puede evitar actualizando a una versión posterior de .NET Framework. También puede evitarse eliminando cualquier LSP de Winsock distinto de IFS que haya instalado.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Secundaria|
|Versión|4.5|
|Tipo|Tiempo de ejecución

#### <a name="affected-apis"></a>API afectadas

-<xref:System.Data.SqlClient.SqlConnection.Open?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlConnection.OpenAsync(System.Threading.CancellationToken)?displayProperty=nameWithType></li></ul>|
