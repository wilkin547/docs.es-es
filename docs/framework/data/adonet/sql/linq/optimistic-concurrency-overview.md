---
title: 'Simultaneidad optimista: Información general'
ms.date: 03/30/2017
ms.assetid: c2e38512-d0c8-4807-b30a-cb7e30338694
ms.openlocfilehash: fa7d423c0abc07e0d97f7d0d4d557aa11d675ee4
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70792929"
---
# <a name="optimistic-concurrency-overview"></a>Simultaneidad optimista: Información general
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite el control de simultaneidad optimista. En la tabla siguiente se describen los términos que se aplican [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] a la simultaneidad optimista en la documentación de:  
  
|Términos|DESCRIPCIÓN|  
|-----------|-----------------|  
|concurrency|Situación en la que dos o más usuarios intentan actualizar la misma fila de la base de datos al mismo tiempo.|  
|Conflicto de simultaneidad|Situación en la cual dos o más usuarios intentan enviar valores incompatibles a una o más columnas de una fila al mismo tiempo.|  
|control de simultaneidad|Técnica utilizada para resolver los conflictos de simultaneidad.|  
|control de simultaneidad optimista|Técnica que primero investiga si otras transacciones han cambiado los valores de una fila antes de permitir que se envíen los cambios.<br /><br /> Contraste con el *control de simultaneidad pesimista*, que bloquea el registro para evitar conflictos de simultaneidad.<br /><br /> El control *optimista* se denomina de este modo porque tiene en cuenta las posibilidades de que una transacción interfiera con otra no sea probable.|  
|Resolución de conflictos|Proceso mediante el cual un elemento en conflicto se actualiza volviendo a consultar la base de datos y resolviendo las diferencias.<br /><br /> Cuando un objeto se actualiza, el seguimiento de cambios de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] conserva los datos siguientes:<br /><br /> : Los valores tomados originalmente de la base de datos y se usan para la comprobación de actualización.<br />-Los nuevos valores de la base de datos de la consulta posterior.<br /><br /> Después, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] determina si el objeto está en conflicto (es decir, si uno o más de sus valores de miembro ha cambiado). Si el objeto está en conflicto, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] Next determina cuál de sus miembros está en conflicto.<br /><br /> Cualquier conflicto de miembro que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] detecta se agrega a una lista de conflictos.|  
  
 En el [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modelo de objetos de, se produce un *conflicto de simultaneidad optimista* cuando se cumplen las dos condiciones siguientes:  
  
- El cliente intenta enviar cambios a la base de datos.  
  
- Uno o más valores de comprobación de actualizaciones se han actualizado en la base de datos desde la última vez que el cliente los leyó.  
  
 Para resolver el conflicto, primero se detectan los miembros del objeto que están en conflicto y, después, se decide qué hacer.  
  
> [!NOTE]
> Solo los miembros asignados como <xref:System.Data.Linq.Mapping.UpdateCheck.Always> o <xref:System.Data.Linq.Mapping.UpdateCheck.WhenChanged> participan en las comprobaciones de simultaneidad optimista. No se realiza ninguna comprobación para los miembros marcados como <xref:System.Data.Linq.Mapping.UpdateCheck.Never>. Para obtener más información, consulta <xref:System.Data.Linq.Mapping.UpdateCheck>.  
  
## <a name="example"></a>Ejemplo  
 Por ejemplo, en el escenario siguiente, User1 empieza a preparar una actualización consultando una fila en la base de datos. User1 recibe una fila con los valores Alfreds, Maria y Sales.  
  
 User1 desea cambiar el valor de la columna Manager a Alfred y el valor de la columna Department a Marketing. Antes de que User1 pudiera enviar los cambios, User2 ha enviado cambios a la base de datos. Por lo tanto, ahora el valor de la columna Assistant ha cambiado a Mary y el valor de la columna Department a Service.  
  
 Cuando User1 intenta enviar los cambios, se produce un error en el envío y se inicia una excepción <xref:System.Data.Linq.ChangeConflictException>. Esto es consecuencia de que los valores de base de datos para la columna Assistant y la columna Department no son los esperados. Los miembros que representan las columnas Assistant y Department están en conflicto. En la tabla siguiente se resume la situación.  
  
||Administrador|Asistente|department|  
|------|-------------|---------------|----------------|  
|Estado original|Alfreds|Maria|Ventas|  
|User1|Alfred||Marketing|  
|User2||Mary|Servicio|  
  
 Puede resolver conflictos como estos de maneras diferentes. Para obtener más información, vea [Cómo: Administrar conflictos](how-to-manage-change-conflicts.md)de cambios.  
  
## <a name="conflict-detection-and-resolution-checklist"></a>Lista de comprobación para detectar y resolver conflictos  
 Puede detectar y resolver los conflictos en cualquier nivel de detalle. Por una parte, puede resolver todos los conflictos de una de tres maneras (vea <xref:System.Data.Linq.RefreshMode>) sin consideraciones adicionales. En el otro extremo, puede designar una acción concreta para cada tipo de conflicto en cada miembro en conflicto.  
  
- Especifique o revise las opciones de <xref:System.Data.Linq.Mapping.UpdateCheck> en su modelo de objetos.  
  
     Para obtener más información, vea [Cómo: Especifique los miembros que se van a probar para](how-to-specify-which-members-are-tested-for-concurrency-conflicts.md)detectar conflictos de simultaneidad.  
  
- En el bloque la try/catch de la llamada a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, especifique en qué punto desea que se inicien excepciones.  
  
     Para obtener más información, consulte [Cómo Especifique cuándo se inician](how-to-specify-when-concurrency-exceptions-are-thrown.md)las excepciones de simultaneidad.  
  
- Determine cuántos detalles del conflicto desea recuperar e incluya el código correspondiente en el bloque try/catch.  
  
     Para obtener más información, consulte [Cómo Recuperar información](how-to-retrieve-entity-conflict-information.md) de conflictos de [entidades y cómo: Recuperar información](how-to-retrieve-member-conflict-information.md)de conflictos de miembros.  
  
- Incluya en el `try` /códigocómodesea resolverlosdistintosconflictosquedetecta`catch` .  
  
     Para obtener más información, vea [Cómo: Resolver conflictos conservando los valores](how-to-resolve-conflicts-by-retaining-database-values.md)de la base de datos, [cómo: Solucione los conflictos sobrescribiendo los](how-to-resolve-conflicts-by-overwriting-database-values.md)valores de [la base de datos y cómo: Resuelva los conflictos combinando con los](how-to-resolve-conflicts-by-merging-with-database-values.md)valores de la base de datos.  
  
## <a name="linq-to-sql-types-that-support-conflict-discovery-and-resolution"></a>Tipos LINQ to SQL que admiten la detección y resolución de conflictos  
 Entre las clases y características que admiten la resolución de conflictos de simultaneidad optimista en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], se incluyen:  
  
- <xref:System.Data.Linq.ObjectChangeConflict?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.MemberChangeConflict?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.ChangeConflictCollection?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.ChangeConflictException?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.DataContext.ChangeConflicts%2A?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.DataContext.SubmitChanges%2A?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.DataContext.Refresh%2A?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.Mapping.UpdateCheck?displayProperty=nameWithType>  
  
- <xref:System.Data.Linq.RefreshMode?displayProperty=nameWithType>  
  
## <a name="see-also"></a>Vea también

- [Cómo: Administrar conflictos de cambios](how-to-manage-change-conflicts.md)
