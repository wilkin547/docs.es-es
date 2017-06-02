---
title: "C&#243;mo: Resolver conflictos conservando valores de la base de datos | Microsoft Docs"
ms.custom: ""
ms.date: "03/30/2017"
ms.prod: ".net-framework-4.6"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "dotnet-ado"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: b475cf72-9e64-4f6e-99c1-af7737bc85ef
caps.latest.revision: 2
author: "JennieHubbard"
ms.author: "jhubbard"
manager: "jhubbard"
caps.handback.revision: 2
---
# C&#243;mo: Resolver conflictos conservando valores de la base de datos
Para resolver las diferencias entre los valores de base de datos esperados y reales antes de intentar reenviar los cambios, puede utilizar <xref:System.Data.Linq.RefreshMode> para conservar los valores que se encuentran en la base de datos.  Los valores actuales del modelo de objetos se sobrescriben.  Para obtener más información, consulta [Simultaneidad optimista: Información general](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
> [!NOTE]
>  En todos los casos, al recuperar los datos actualizados de la base de datos se actualiza en primer lugar el registro en el cliente.  Esta acción garantiza que el siguiente intento de actualización no producirá errores en las mismas comprobaciones de simultaneidad.  
  
## Ejemplo  
 En este escenario, se inicia una excepción <xref:System.Data.Linq.ChangeConflictException> cuando User1 intenta enviar los cambios, porque User2 ha cambiado en ese período de tiempo las columnas Assistant y Department.  En la tabla siguiente se muestra la situación.  
  
||Administrador|Asistente|Department|  
|------|-------------------|---------------|----------------|  
|Estado de la base de datos original cuando la consultan User1 y User2.|Alfreds|Maria|Ventas|  
|User1 se prepara para enviar los cambios.|Alfred||Marketing|  
|User2 ya ha enviado los cambios.||Mary|Servicio|  
  
 User1 decide resolver este conflicto haciendo que los valores más nuevos de la base de datos sobrescriban los valores actuales del modelo de objetos.  
  
 Cuando User1 resuelve el conflicto utilizando <xref:System.Data.Linq.RefreshMode>, el resultado en la base de datos es el de la tabla siguiente:  
  
||Administrador|Asistente|Department|  
|------|-------------------|---------------|----------------|  
|Nuevo estado tras la resolución del conflicto.|Alfreds<br /><br /> \(original\)|Mary<br /><br /> \(de User2\)|Servicio<br /><br /> \(de User2\)|  
  
 El código de ejemplo siguiente muestra cómo sobrescribir los valores actuales del modelo de objetos con los valores de la base de datos.  \(No se produce ninguna inspección o control personalizado de los conflictos entre miembros individuales.\)  
  
 [!code-csharp[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#1)]  
  
## Vea también  
 [Cómo: Administrar los conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)