---
description: Más información acerca de las operaciones de inserción, actualización y eliminación
title: Operaciones de actualización, inserción y eliminación
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 26a43a4f-83c9-4732-806d-bb23aad0ff6b
ms.openlocfilehash: 2d0470ed6abe654ca08f954c3de97de207adb75d
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 02/06/2021
ms.locfileid: "99803824"
---
# <a name="insert-update-and-delete-operations"></a>Operaciones de actualización, inserción y eliminación

En `Insert`, las operaciones `Update`, `Delete` y [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] se realizan agregando, cambiando y quitando objetos en el modelo de objetos. De forma predeterminada, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] convierte estas acciones a SQL y envía los cambios a la base de datos.

[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] ofrece la máxima flexibilidad para manipular y conservar los cambios realizados en los objetos. En cuanto están disponibles los objetos entidad (ya sea recuperándolos a través de una consulta o construyéndolos nuevamente), puede cambiarlos como los objetos normales de la aplicación. Es decir, puede cambiar sus valores, agregarlos a las colecciones y quitarlos de las mismas. [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] realiza un seguimiento de los cambios y está listo para volver a transmitirlos a la base de datos cuando llame al método <xref:System.Data.Linq.DataContext.SubmitChanges%2A>.

> [!NOTE]
> [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] no admite ni reconoce las operaciones de eliminación en cascada. Si desea eliminar una fila de una tabla que tiene restricciones, debe establecer la `ON DELETE CASCADE` regla en la restricción FOREIGN KEY en la base de datos, o bien usar su propio código para eliminar primero los objetos secundarios que impiden que se elimine el objeto primario. De lo contrario, se inicia una excepción. Para obtener más información, consulte [Cómo: eliminar filas de la base de datos](how-to-delete-rows-from-the-database.md).

En los siguientes extractos se utilizan las clases `Customer` y `Order` de la base de datos de ejemplo Northwind. Para no extendernos demasiado, no incluimos las definiciones de clase.

[!code-csharp[DLinqCRUDOps#1](../../../../../../samples/snippets/csharp/VS_Snippets_Data/DLinqCRUDOps/cs/Program.cs#1)]
[!code-vb[DLinqCRUDOps#1](../../../../../../samples/snippets/visualbasic/VS_Snippets_Data/DLinqCRUDOps/vb/Module1.vb#1)]

Al llamar a <xref:System.Data.Linq.DataContext.SubmitChanges%2A>, [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] genera y ejecuta automáticamente los comandos SQL necesarios para volver a transmitir los cambios a la base de datos.

> [!NOTE]
> Puede invalidar este comportamiento utilizando su propia lógica personalizada, normalmente mediante un procedimiento almacenado. Para obtener más información, consulte [responsabilidades del Desarrollador en invalidar el comportamiento predeterminado](responsibilities-of-the-developer-in-overriding-default-behavior.md).
>
> Los desarrolladores que usan Visual Studio pueden usar el Object Relational Designer para desarrollar procedimientos almacenados con este fin.

## <a name="see-also"></a>Vea también

- [Descargar bases de datos de ejemplo](downloading-sample-databases.md)
- [Personalizar operaciones de actualización, inserción y eliminación](customizing-insert-update-and-delete-operations.md)
