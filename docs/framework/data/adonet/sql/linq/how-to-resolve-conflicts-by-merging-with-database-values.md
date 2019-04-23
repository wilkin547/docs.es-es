---
title: Procedimiento para resolver conflictos mediante combinaciones con valores de base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1988b79c-3bfc-4c5c-a08a-86cf638bbe17
ms.openlocfilehash: 429bca7501bd58440ee894345855141a2a2ed12c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59130213"
---
# <a name="how-to-resolve-conflicts-by-merging-with-database-values"></a>Procedimiento para resolver conflictos mediante combinaciones con valores de base de datos
Para conciliar las diferencias entre los valores de base de datos esperados y reales antes de intentar reenviar los cambios, puede utilizar <xref:System.Data.Linq.RefreshMode.KeepChanges> para combinar los valores de base de datos con los valores de miembro de cliente actuales. Para obtener más información, consulte [simultaneidad optimista: Información general sobre](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
> [!NOTE]
>  En todos los casos, al recuperar los datos actualizados de la base de datos se actualiza en primer lugar el registro en el cliente. Esta acción garantiza que el siguiente intento de actualización no producirá errores en las mismas comprobaciones de simultaneidad.  
  
## <a name="example"></a>Ejemplo  
 En este escenario, se inicia una excepción <xref:System.Data.Linq.ChangeConflictException> cuando User1 intenta enviar los cambios, porque User2 ha cambiado en ese período de tiempo las columnas Assistant y Department. En la tabla siguiente se muestra la situación.  
  
||Administrador|Asistente|Department|  
|------|-------------|---------------|----------------|  
|Estado de la base de datos original cuando la consultan User1 y User2.|Alfreds|Maria|Ventas|  
|User1 se prepara para enviar los cambios.|Alfred||Marketing|  
|User2 ya ha enviado los cambios.||Mary|web de Office|  
  
 User1 decide resolver este conflicto combinando los valores de la base de datos con los valores de miembro de cliente actuales. El resultado será que los valores de la base de datos se sobrescribirán cuando el conjunto de cambios actual haya modificado también ese valor.  
  
 Cuando User1 resuelve el conflicto utilizando <xref:System.Data.Linq.RefreshMode.KeepChanges>, el resultado en la base de datos es como en la tabla siguiente:  
  
||Administrador|Asistente|Department|  
|------|-------------|---------------|----------------|  
|Nuevo estado tras la resolución del conflicto.|Alfred<br /><br /> (de User1)|Mary<br /><br /> (de User2)|Marketing<br /><br /> (de User1)|  
  
 En el ejemplo siguiente se muestra cómo combinar los valores de la base de datos con los valores de miembro de cliente actuales (a menos que el cliente también haya cambiado ese valor). No se produce ninguna inspección o control personalizado de los conflictos entre miembros individuales.  
  
 [!code-csharp[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#3)]
 [!code-vb[System.Data.Linq.RefreshMode#3](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#3)]  
  
## <a name="see-also"></a>Vea también

- [Cómo: Resolver conflictos de simultaneidad sobrescribiendo valores de la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-overwriting-database-values.md)
- [Cómo: Resolver conflictos de simultaneidad conservando valores de la base de datos](../../../../../../docs/framework/data/adonet/sql/linq/how-to-resolve-conflicts-by-retaining-database-values.md)
- [Cómo: Administrar conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
