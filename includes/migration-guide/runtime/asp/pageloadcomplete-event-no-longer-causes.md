---
ms.openlocfilehash: 39d609c955596354d1af28b4ed19d367dab0462b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620538"
---
### <a name="pageloadcomplete-event-no-longer-causes-systemwebuiwebcontrolsentitydatasource-control-to-invoke-data-binding"></a>El evento Page.LoadComplete ya no hace que el control System.Web.UI.WebControls.EntityDataSource invoque un enlace de datos

#### <a name="details"></a>Detalles

El evento <xref:System.Web.UI.Page.LoadComplete> ya no hace que el control <xref:System.Web.UI.WebControls.EntityDataSource?displayProperty=fullName> llame al enlace de datos cuando se producen cambios al crear, actualizar o eliminar parámetros. Este cambio elimina un viaje superfluo a la base de datos, impide que se restablezcan los valores de los controles y produce un comportamiento coherente con otros controles de datos, como <xref:System.Web.UI.WebControls.SqlDataSource?displayProperty=fullName> y <xref:System.Web.UI.WebControls.ObjectDataSource?displayProperty=fullName>. Este cambio produce un comportamiento diferente en el caso improbable de que las aplicaciones invoquen el enlace de datos en el evento <xref:System.Web.UI.Page.LoadComplete>.

#### <a name="suggestion"></a>Sugerencia

Si se necesita un enlace de datos, invóquelo manualmente en un evento anterior en la devolución.

| NOMBRE    | Valor       |
|:--------|:------------|
| Ámbito   |Borde|
|Versión|4.5|
|Tipo|Tiempo de ejecución|
