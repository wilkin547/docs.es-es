---
title: "Cómo: consultar una base de datos usando LINQ (Visual Basic) | Documentos de Microsoft"
ms.custom: 
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- query samples [LINQ]
- database querying [LINQ]
- queries [LINQ in Visual Basic], database querying
- querying databases [LINQ]
- queries [LINQ in Visual Basic], how-to topics
- query samples [Visual Basic]
ms.assetid: bcf5e9c3-a236-4399-9a7f-3991eca7cf56
caps.latest.revision: 12
author: stevehoag
ms.author: shoag
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: a88a7172f48012d12bf0bb3089bffb510e786c3b
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-query-a-database-by-using-linq-visual-basic"></a>Cómo: Consultar una base de datos usando LINQ (Visual Basic)
Language-Integrated Query (LINQ) facilita el acceso a la información de la base de datos y ejecutar consultas.  
  
 En el ejemplo siguiente se muestra cómo crear una nueva aplicación que realiza consultas en una base de datos de SQL Server.  
  
 Los ejemplos de este tema utilizan la base de datos de ejemplo Northwind. Si no tiene la base de datos de ejemplo Northwind en el equipo de desarrollo, puede descargarla desde el [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) sitio Web. Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](https://msdn.microsoft.com/library/bb399411).  
  
[!INCLUDE[note_settings_general](../../../../csharp/language-reference/compiler-messages/includes/note_settings_general_md.md)]  
  
## <a name="to-create-a-connection-to-a-database"></a>Para crear una conexión a una base de datos  
  
1.  En Visual Studio, abra **Explorador de servidores**/**Database Explorer** haciendo clic en **Explorador de servidores**/**Database Explorer** en el **vista** menú.  
  
2.  Haga clic en **las conexiones de datos** en **Explorador de servidores**/**Database Explorer** y, a continuación, haga clic en **Agregar conexión**.  
  
3.  Especifique una conexión válida a la base de datos de ejemplo Northwind.  
  
## <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Para agregar un proyecto que contiene un archivo de LINQ to SQL  
  
1.  En Visual Studio, en el **archivo** menú, seleccione **nueva** y, a continuación, haga clic en **proyecto**. Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.  
  
2.  En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**. Seleccione el **clases LINQ to SQL** plantilla de elemento.  
  
3.  Nombre de archivo `northwind.dbml`. Haga clic en **Agregar**. Se abre el Object Relational Designer (Object Relational Designer) para el archivo northwind.dbml.  
  
## <a name="to-add-tables-to-query-to-the-or-designer"></a>Para agregar tablas a la consulta para el Object Relational Designer  
  
1.  En **Explorador de servidores**/**Database Explorer**, expanda la conexión de la base de datos Northwind. Expanda el **tablas** carpeta.  
  
     Si ha cerrado el Object Relational Designer, puede volver a abrirlo haciendo doble clic en el archivo northwind.dbml que agregó anteriormente.  
  
2.  Haga clic en la tabla Customers y arrástrela hasta el panel izquierdo del diseñador. Haga clic en la tabla Orders y arrástrelo hasta el panel izquierdo del diseñador.  
  
     El diseñador crea nuevos `Customer` y `Order` objetos para el proyecto. Observe que el diseñador automáticamente detecta las relaciones entre las tablas y los crea a secundarios propiedades de objetos relacionados. Por ejemplo, IntelliSense mostrará que el `Customer` objeto tiene una `Orders` propiedad para todos los pedidos relacionados con ese cliente.  
  
3.  Guarde los cambios y cierre el diseñador.  
  
4.  Guarde el proyecto.  
  
## <a name="to-add-code-to-query-the-database-and-display-the-results"></a>Para agregar código para consultar la base de datos y mostrar los resultados  
  
1.  Desde el **herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView>control en el formulario Windows Forms predeterminado del proyecto, Form1.</xref:System.Windows.Forms.DataGridView>  
  
2.  Haga doble clic en Form1 para agregar código a la `Load` evento del formulario.  
  
3.  Cuando agrega tablas a Object Relational Designer, el diseñador agrega un <xref:System.Data.Linq.DataContext>objeto para su proyecto.</xref:System.Data.Linq.DataContext> Este objeto contiene el código que debe tener para obtener acceso a esas tablas, además de los objetos individuales y colecciones de cada tabla. La <xref:System.Data.Linq.DataContext>objeto para su proyecto se denomina según el nombre del archivo .dbml.</xref:System.Data.Linq.DataContext> Para este proyecto, el <xref:System.Data.Linq.DataContext>se denomina objeto `northwindDataContext`.</xref:System.Data.Linq.DataContext>  
  
     Puede crear una instancia de la <xref:System.Data.Linq.DataContext>en el código y consultar las tablas especifican por el Object Relational Designer.</xref:System.Data.Linq.DataContext>  
  
     Agregue el código siguiente a la `Load` eventos para consultar las tablas que se exponen como propiedades del contexto de datos.  
  
     [!code-vb[VbLINQToSQLHowTos&3;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_1.vb)]  
  
4.  Presione F5 para ejecutar el proyecto y ver los resultados.  
  
5.  Siguientes son algunas consultas adicionales que puede probar:  
  
     [!code-vb[VbLINQToSQLHowTos Nº&4;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_2.vb)]  
    [!code-vb[VbLINQToSQLHowTos&#5;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-query-a-database-by-using-linq_3.vb)]  
  
## <a name="see-also"></a>Vea también  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)   
 [Métodos de DataContext (Object Relational Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)

