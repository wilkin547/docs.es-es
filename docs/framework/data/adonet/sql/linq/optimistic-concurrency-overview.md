---
title: "Simultaneidad optimista: Informaci&#243;n general | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c2e38512-d0c8-4807-b30a-cb7e30338694
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# Simultaneidad optimista: Informaci&#243;n general
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] admite el control de simultaneidad optimista.  En la tabla siguiente se describen los términos que se refieren a la simultaneidad optimista en la documentación de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]:  
  
|Términos|Descripción|  
|--------------|-----------------|  
|simultaneidad|Situación en la que dos o más usuarios intentan actualizar la misma fila de la base de datos al mismo tiempo.|  
|Conflicto de simultaneidad|Situación en la cual dos o más usuarios intentan enviar valores incompatibles a una o más columnas de una fila al mismo tiempo.|  
|control de simultaneidad|Técnica utilizada para resolver los conflictos de simultaneidad.|  
|control de simultaneidad optimista|Técnica que primero investiga si otras transacciones han cambiado los valores de una fila antes de permitir que se envíen los cambios.<br /><br /> Por otra parte, se encuentra el *control de simultaneidad pesimista*, que bloquea el registro para evitar los conflictos de simultaneidad.<br /><br /> El control *optimista* se denomina así porque considera que son escasas las posibilidades de que una transacción interfiera con otra.|  
|Resolución de conflictos|Proceso mediante el cual un elemento en conflicto se actualiza volviendo a consultar la base de datos y resolviendo las diferencias.<br /><br /> Cuando un objeto se actualiza, el seguimiento de cambios de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] conserva los datos siguientes:<br /><br /> -   Los valores tomados originalmente de la base de datos y utilizados para la comprobación de actualizaciones.<br />-   Los nuevos valores de la base de datos obtenidos en la consulta posterior.<br /><br /> Después, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] determina si el objeto está en conflicto \(es decir, si uno o más de sus valores de miembro ha cambiado\).  Si el objeto está en conflicto, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] determina cuál de sus miembros lo está.<br /><br /> Cualquier conflicto de miembro que [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] detecta se agrega a una lista de conflictos.|  
  
 En el modelo de objetos de [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], se produce un *conflicto de simultaneidad optimista* cuando se dan las dos condiciones siguientes:  
  
-   El cliente intenta enviar cambios a la base de datos.  
  
-   Uno o más valores de comprobación de actualizaciones se han actualizado en la base de datos desde la última vez que el cliente los leyó.  
  
 Para resolver el conflicto, primero se detectan los miembros del objeto que están en conflicto y, después, se decide qué hacer.  
  
> [!NOTE]
>  Solo los miembros asignados como <xref:System.Data.Linq.Mapping.UpdateCheck> o <xref:System.Data.Linq.Mapping.UpdateCheck> participan en las comprobaciones de simultaneidad optimista.  No se realiza ninguna comprobación para los miembros marcados como <xref:System.Data.Linq.Mapping.UpdateCheck>.  Para obtener más información, consulta <xref:System.Data.Linq.Mapping.UpdateCheck>.  
  
## Ejemplo  
 Por ejemplo, en el escenario siguiente, User1 empieza a preparar una actualización consultando una fila en la base de datos.  User1 recibe una fila con los valores Alfreds, Maria y Sales.  
  
 User1 desea cambiar el valor de la columna Manager a Alfred y el valor de la columna Department a Marketing.  Antes de que User1 pudiera enviar los cambios, User2 ha enviado cambios a la base de datos.  Por lo tanto, ahora el valor de la columna Assistant ha cambiado a Mary y el valor de la columna Department a Service.  
  
 Cuando User1 intenta enviar los cambios, se produce un error en el envío y se inicia una excepción <xref:System.Data.Linq.ChangeConflictException>.  Esto es consecuencia de que los valores de base de datos para la columna Assistant y la columna Department no son los esperados.  Los miembros que representan las columnas Assistant y Department están en conflicto.  En la tabla siguiente se resume la situación.  
  
||Administrador|Asistente|Department|  
|------|-------------------|---------------|----------------|  
|Estado original|Alfreds|Maria|Ventas|  
|User1|Alfred||Marketing|  
|User2||Mary|Servicio|  
  
 Puede resolver conflictos como estos de maneras diferentes.  Para obtener más información, consulta [Cómo: Administrar los conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md).  
  
## Lista de comprobación para detectar y resolver conflictos  
 Puede detectar y resolver los conflictos en cualquier nivel de detalle.  Por una parte, puede resolver todos los conflictos de una de tres maneras \(vea <xref:System.Data.Linq.RefreshMode>\) sin consideraciones adicionales.  En el otro extremo, puede designar una acción concreta para cada tipo de conflicto en cada miembro en conflicto.  
  
-   Especifique o revise las opciones de <xref:System.Data.Linq.Mapping.UpdateCheck> en su modelo de objetos.  
  
     Para obtener más información, consulta [Cómo: Especificar los miembros que se comprueban en conflictos de simultaneidad](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-which-members-are-tested-for-concurrency-conflicts.md).  
  
-   En el bloque la try\/catch de la llamada a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, especifique en qué punto desea que se inicien excepciones.  
  
     Para obtener más información, consulta [Cómo: Especificar cuándo se producen excepciones de simultaneidad](../../../../../../docs/framework/data/adonet/sql/linq/how-to-specify-when-concurrency-exceptions-are-thrown.md).  
  
-   Determine cuántos detalles del conflicto desea recuperar e incluya el código correspondiente en el bloque try\/catch.  
  
     Para obtener más información, vea [Cómo: Recuperar información sobre conflictos de simultaneidad](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-entity-conflict-information.md) y [Cómo: Recuperar información sobre conflictos entre miembros](../../../../../../docs/framework/data/adonet/sql/linq/how-to-retrieve-member-conflict-information.md).  
  
-   Indique en el código `try`\/`catch` cómo desea resolver los distintos conflictos que detecte.  
  
     Para obtener más información, vea [Cómo: Resolver conflictos conservando valores de la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md), [Cómo: Resolver conflictos invalidando valores de la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md) y [Cómo: Resolver conflictos combinando con valores de la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-merging-with-database-values.md).  
  
## Tipos LINQ to SQL que admiten la detección y resolución de conflictos  
 Entre las clases y características que admiten la resolución de conflictos de simultaneidad optimista en [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], se incluyen:  
  
-   <xref:System.Data.Linq.ObjectChangeConflict?displayProperty=fullName>  
  
-   <xref:System.Data.Linq.MemberChangeConflict?displayProperty=fullName>  
  
-   <xref:System.Data.Linq.ChangeConflictCollection?displayProperty=fullName>  
  
-   <xref:System.Data.Linq.ChangeConflictException?displayProperty=fullName>  
  
-   <xref:System.Data.Linq.DataContext.ChangeConflicts%2A?displayProperty=fullName>  
  
-   <xref:System.Data.Linq.DataContext.SubmitChanges%2A?displayProperty=fullName>  
  
-   <xref:System.Data.Linq.DataContext.Refresh%2A?displayProperty=fullName>  
  
-   <xref:System.Data.Linq.Mapping.ColumnAttribute.UpdateCheck%2A?displayProperty=fullName>  
  
-   <xref:System.Data.Linq.Mapping.UpdateCheck?displayProperty=fullName>  
  
-   <xref:System.Data.Linq.RefreshMode?displayProperty=fullName>  
  
## Vea también  
 [Cómo: Administrar los conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)