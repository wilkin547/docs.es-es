---
title: Filtrar para resolver conflictos sobrescribiendo valores de base de datos
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: fd6db0b8-c29c-48ff-b768-31d28e7a148c
ms.openlocfilehash: 7b8d7cf8ab2335c064062ed3ab4072d81e8042fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 04/08/2019
ms.locfileid: "59189123"
---
# <a name="how-to-resolve-conflicts-by-overwriting-database-values"></a>Filtrar para resolver conflictos sobrescribiendo valores de base de datos
Para conciliar las diferencias existentes entre los valores de base de datos esperados y reales antes de intentar reenviar los cambios, puede utilizar <xref:System.Data.Linq.RefreshMode.KeepCurrentValues> para sobrescribir los valores de base de datos. Para obtener más información, consulte [simultaneidad optimista: Información general sobre](../../../../../../docs/framework/data/adonet/sql/linq/optimistic-concurrency-overview.md).  
  
> [!NOTE]
>  En todos los casos, al recuperar los datos actualizados de la base de datos se actualiza en primer lugar el registro en el cliente. Esta acción garantiza que el siguiente intento de actualización no producirá errores en las mismas comprobaciones de simultaneidad.  
  
## <a name="example"></a>Ejemplo  
 En este escenario, se inicia una excepción <xref:System.Data.Linq.ChangeConflictException> cuando User1 intenta enviar los cambios, porque User2 ha cambiado en ese período de tiempo las columnas Assistant y Department. En la tabla siguiente se muestra la situación.  
  
||Administrador|Asistente|Department|  
|------|-------------|---------------|----------------|  
|Estado de la base de datos original cuando la consultan User1 y User2.|Alfreds|Maria|Ventas|  
|User1 se prepara para enviar los cambios.|Alfred||Marketing|  
|User2 ya ha enviado los cambios.||Mary|web de Office|  
  
 User1 decide resolver este conflicto sobrescribiendo los valores de la base de datos con los valores de miembro de cliente actuales.  
  
 Cuando User1 resuelve el conflicto utilizando <xref:System.Data.Linq.RefreshMode.KeepCurrentValues>, el resultado en la base de datos es como en la tabla siguiente:  
  
||Administrador|Asistente|Department|  
|------|-------------|---------------|----------------|  
|Nuevo estado tras la resolución del conflicto.|Alfred<br /><br /> (de User1)|Maria<br /><br /> (original)|Marketing<br /><br /> (de User1)|  
  
 En el siguiente ejemplo de código se muestra cómo sobrescribir los valores de base de datos con los valores de miembro de cliente actuales. (No se produce ninguna inspección o control personalizado de los conflictos entre miembros individuales.)  
  
 [!code-csharp[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/csharp/VS_Snippets_Data/system.data.linq.refreshmode/cs/program.cs#2)]
 [!code-vb[System.Data.Linq.RefreshMode#2](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/system.data.linq.refreshmode/vb/module1.vb#2)]  
  
## <a name="see-also"></a>Vea también

- [Filtrar para administrar conflictos de cambios](../../../../../../docs/framework/data/adonet/sql/linq/how-to-manage-change-conflicts.md)
