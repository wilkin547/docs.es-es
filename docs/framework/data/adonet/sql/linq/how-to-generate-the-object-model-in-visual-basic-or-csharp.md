---
title: Procedimiento para generar el modelo de objetos en Visual Basic o C#
ms.date: 03/30/2017
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
ms.openlocfilehash: 8752a28b9bcfd068afcfc5d33c3097f26cf0f231
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59225370"
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a>Procedimiento Generar el modelo de objetos en Visual Basic o C\#
En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], un modelo de objetos en un lenguaje de programación se asigna a una base de datos relacional. Existen dos herramientas para generar automáticamente un Visual Basic o C# modelos de los metadatos de una base de datos existente.  
  
-   Si utiliza Visual Studio, puede usar el [!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)] para generar un modelo de objetos. El [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] proporciona una interfaz de usuario enriquecida para ayudarle a generar un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modelo de objetos. Para obtener más información, vea [Linq to SQL Tools en Visual Studio](https://docs.microsoft.com/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).
  
-   Herramienta de línea de comandos SQLMetal Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
    > [!NOTE]
    >  Si no tiene una base de datos existente y desear crear una a partir de un modelo de objetos, puede crear el modelo de objetos mediante el editor de código y <xref:System.Data.Linq.DataContext.CreateDatabase%2A>. Para obtener más información, vea [Cómo: Crear dinámicamente una base de datos](../../../../../../docs/framework/data/adonet/sql/linq/how-to-dynamically-create-a-database.md).  
  
 Documentación para el [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)] se proporcionan ejemplos de cómo generar un Visual Basic o C# modelo de objetos mediante el uso de la [!INCLUDE[vs_ordesigner_short](../../../../../../includes/vs-ordesigner-short-md.md)]. En la información siguiente se proporcionan ejemplos del uso de la herramienta de línea de comandos de SQLMetal. Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Ejemplo  
 La línea de comandos de SQLMetal que se muestra en el ejemplo siguiente genera el código de Visual Basic como el modelo de objetos basado en atributos de la base de datos de ejemplo Northwind. Se presentan también los procedimientos almacenados y las funciones.  
  
```  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a>Ejemplo  
 La línea de comandos de SQLMetal mostrada en el ejemplo siguiente genera código de C# como el modelo de objetos basado en atributos de la base de datos de ejemplo Northwind. Se presentan también los procedimientos almacenados y las funciones, y los nombres de tabla se pluralizan automáticamente.  
  
```  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a>Vea también

- [Guía de programación](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)
- [Modelo de objetos de LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/the-linq-to-sql-object-model.md)
- [Aprendizaje con tutoriales](../../../../../../docs/framework/data/adonet/sql/linq/learning-by-walkthroughs.md)
- [Cómo: Personalizar las clases de entidad mediante el Editor de código](../../../../../../docs/framework/data/adonet/sql/linq/how-to-customize-entity-classes-by-using-the-code-editor.md)
- [Asignación basada en atributos](../../../../../../docs/framework/data/adonet/sql/linq/attribute-based-mapping.md)
- [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
- [Asignación externa](../../../../../../docs/framework/data/adonet/sql/linq/external-mapping.md)
- [Descargar bases de datos de ejemplo](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)
- [Creación del modelo de objetos](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
