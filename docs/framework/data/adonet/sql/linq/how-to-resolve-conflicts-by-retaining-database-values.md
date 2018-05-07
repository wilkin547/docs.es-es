---
title: 'Cómo: Resolver conflictos de simultaneidad conservando valores de base de datos'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: b475cf72-9e64-4f6e-99c1-af7737bc85ef
ms.openlocfilehash: d0d59c520beaab2d6c8c1594ee81a3eaecf1d03e
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-resolve-conflicts-by-retaining-database-values"></a>Cómo: Resolver conflictos de simultaneidad conservando valores de base de datos
Para resolver las diferencias entre los valores de base de datos esperados y reales antes de intentar reenviar los cambios, puede utilizar <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues> para conservar los valores que se encuentran en la base de datos. Los valores actuales del modelo de objetos se sobrescriben. Para obtener más información, consulte [simultaneidad optimista: información general sobre](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
> [!NOTE]
>  En todos los casos, al recuperar los datos actualizados de la base de datos se actualiza en primer lugar el registro en el cliente. Esta acción garantiza que el siguiente intento de actualización no producirá errores en las mismas comprobaciones de simultaneidad.  
  
## <a name="example"></a>Ejemplo  
 En este escenario, se inicia una excepción <xref:System.Data.Linq.ChangeConflictException> cuando User1 intenta enviar los cambios, porque User2 ha cambiado en ese período de tiempo las columnas Assistant y Department. En la tabla siguiente se muestra la situación.  
  
||Administrador|Asistente|Department|  
|------|-------------|---------------|----------------|  
|Estado de la base de datos original cuando la consultan User1 y User2.|Alfreds|Maria|Ventas|  
|User1 se prepara para enviar los cambios.|Alfred||Marketing|  
|User2 ya ha enviado los cambios.||Mary|Servicio|  
  
 User1 decide resolver este conflicto haciendo que los valores más nuevos de la base de datos sobrescriban los valores actuales del modelo de objetos.  
  
 Cuando User1 resuelve el conflicto utilizando <xref:System.Data.Linq.RefreshMode.OverwriteCurrentValues>, el resultado en la base de datos es el de la tabla siguiente:  
  
||Administrador|Asistente|Department|  
|------|-------------|---------------|----------------|  
|Nuevo estado tras la resolución del conflicto.|Alfreds<br /><br /> (original)|Mary<br /><br /> (de User2)|Servicio<br /><br /> (de User2)|  
  
 El código de ejemplo siguiente muestra cómo sobrescribir los valores actuales del modelo de objetos con los valores de la base de datos. (No se produce ninguna inspección o control personalizado de los conflictos entre miembros individuales.)  
  
 [!code-csharp[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#1)]
 [!code-vb[System.Data.Linq.RefreshMode#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#1)]  
  
## <a name="see-also"></a>Vea también  
 [Administración de conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
