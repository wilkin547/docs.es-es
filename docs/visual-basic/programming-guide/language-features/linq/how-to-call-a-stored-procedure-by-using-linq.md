---
title: "Cómo: llamar a un procedimiento almacenado usando LINQ (Visual Basic) | Documentos de Microsoft"
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
- queries [LINQ in Visual Basic], stored procedure calls
- stored procedures sample [Visual Basic]
- stored procedures [LINQ to SQL]
- queries [LINQ in Visual Basic], how-to topics
ms.assetid: 6436d384-d1e0-40aa-8afd-451007477260
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: a06bd2a17f1d6c7308fa6337c866c1ca2e7281c0
ms.openlocfilehash: abc3970fc5ab6f4a2f4b67b5efa2b19afb07337b
ms.contentlocale: es-es
ms.lasthandoff: 03/13/2017

---
# <a name="how-to-call-a-stored-procedure-by-using-linq-visual-basic"></a>Cómo: Llamar a un procedimiento almacenado usando LINQ (Visual Basic)
Language-Integrated Query (LINQ) facilita el acceso a la información de la base de datos, incluidos procedimientos almacenados como los objetos de base de datos.  
  
 En el ejemplo siguiente se muestra cómo crear una aplicación que llama a un procedimiento almacenado en una base de datos de SQL Server. El ejemplo muestra cómo llamar a dos procedimientos almacenados diferentes en la base de datos. Cada procedimiento devuelve los resultados de una consulta. Un procedimiento toma parámetros de entrada y el otro procedimiento no toma parámetros.  
  
 Los ejemplos de este tema utilizan la base de datos de ejemplo Northwind. Si no tiene la base de datos de ejemplo Northwind en el equipo de desarrollo, puede descargarla desde el [Microsoft Download Center](http://go.microsoft.com/fwlink/?LinkID=98088) sitio Web. Para obtener instrucciones, consulte [descargar bases de datos de ejemplo](https://msdn.microsoft.com/library/bb399411).  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-a-connection-to-a-database"></a>Para crear una conexión a una base de datos  
  
1.  En Visual Studio, abra **Explorador de servidores**/**Database Explorer** haciendo clic en **Explorador de servidores**/**Database Explorer** en el **vista** menú.  
  
2.  Haga clic en **las conexiones de datos** en **Explorador de servidores**/**Database Explorer** y, a continuación, haga clic en **Agregar conexión**.  
  
3.  Especifique una conexión válida a la base de datos de ejemplo Northwind.  
  
### <a name="to-add-a-project-that-contains-a-linq-to-sql-file"></a>Para agregar un proyecto que contiene un archivo de LINQ to SQL  
  
1.  En Visual Studio, en el **archivo** menú, seleccione **nueva** y, a continuación, haga clic en **proyecto**. Seleccione Visual Basic **aplicación de Windows Forms** como el tipo de proyecto.  
  
2.  En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**. Seleccione el **clases LINQ to SQL** plantilla de elemento.  
  
3.  Nombre de archivo `northwind.dbml`. Haga clic en **Agregar**. Se abre el Object Relational Designer (Object Relational Designer) para el archivo northwind.dbml.  
  
### <a name="to-add-stored-procedures-to-the-or-designer"></a>Agregar procedimientos almacenados a Object Relational Designer  
  
1.  En **Explorador de servidores**/**Database Explorer**, expanda la conexión de la base de datos Northwind. Expanda el **procedimientos almacenados** carpeta.  
  
     Si ha cerrado el Object Relational Designer, puede volver a abrirlo haciendo doble clic en el archivo northwind.dbml que agregó anteriormente.  
  
2.  Haga clic en el **ventas por año** procedimiento almacenado y arrástrelo hasta el panel derecho del diseñador. Haga clic en el **diez productos más caros** procedimiento almacenado arrástrelo hasta el panel derecho del diseñador.  
  
3.  Guarde los cambios y cierre el diseñador.  
  
4.  Guarde el proyecto.  
  
### <a name="to-add-code-to-display-the-results-of-the-stored-procedures"></a>Para agregar código para mostrar los resultados de los procedimientos almacenados  
  
1.  Desde el **cuadro de herramientas**, arrastre un <xref:System.Windows.Forms.DataGridView>control en el formulario Windows Forms predeterminado del proyecto, Form1.</xref:System.Windows.Forms.DataGridView>  
  
2.  Haga doble clic en Form1 para agregar código a su `Load` eventos.  
  
3.  Al agregar los procedimientos almacenados en el Object Relational Designer, el diseñador agrega un <xref:System.Data.Linq.DataContext>objeto para su proyecto.</xref:System.Data.Linq.DataContext> Este objeto contiene el código que debe tener para obtener acceso a esos procedimientos. La <xref:System.Data.Linq.DataContext>objeto para el proyecto se denomina según el nombre del archivo .dbml.</xref:System.Data.Linq.DataContext> Para este proyecto, el <xref:System.Data.Linq.DataContext>se denomina objeto `northwindDataContext`.</xref:System.Data.Linq.DataContext>  
  
     Puede crear una instancia de la <xref:System.Data.Linq.DataContext>en el código y la llamada a los métodos de procedimiento almacenado especifican por el Object Relational Designer.</xref:System.Data.Linq.DataContext> Para enlazar con el <xref:System.Windows.Forms.DataGridView>de objeto, puede que tenga que forzar la consulta se ejecute inmediatamente llamando el <xref:System.Linq.Enumerable.ToList%2A>método en los resultados del procedimiento almacenado.</xref:System.Linq.Enumerable.ToList%2A> </xref:System.Windows.Forms.DataGridView>  
  
     Agregue el código siguiente a la `Load` eventos para llamar a cualquiera de los procedimientos almacenados expuestos como métodos para el contexto de datos.  
  
     [!code-vb[1 VbLINQtoSQLHowTos](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_1.vb)]  
    [!code-vb[VbLINQtoSQLHowTos&#2;](../../../../visual-basic/programming-guide/language-features/linq/codesnippet/VisualBasic/how-to-call-a-stored-procedure-by-using-linq_2.vb)]  
  
4.  Presione F5 para ejecutar el proyecto y ver los resultados.  
  
## <a name="see-also"></a>Vea también  
 [LINQ](../../../../visual-basic/programming-guide/language-features/linq/index.md)   
 [Consultas](../../../../visual-basic/language-reference/queries/queries.md)   
 [LINQ to SQL](https://msdn.microsoft.com/library/bb386976)   
 [Métodos de DataContext (Object Relational Designer)](https://docs.microsoft.com/visualstudio/data-tools/datacontext-methods-o-r-designer)   
 [Cómo: asignar procedimientos almacenados para realizar actualizaciones, inserciones y eliminaciones (Object Relational Designer)](http://msdn.microsoft.com/library/e88224ab-ff61-4a3a-b6b8-6f3694546cac)

