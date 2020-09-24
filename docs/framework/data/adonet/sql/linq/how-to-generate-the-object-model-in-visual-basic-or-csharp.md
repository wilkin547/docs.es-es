---
title: Procedimiento para generar el modelo de objetos en Visual Basic o C#
ms.date: 03/30/2017
ms.assetid: a0c73b33-5650-420c-b9dc-f49310c201ee
ms.openlocfilehash: 03525b6f39dcccfb9c68da6bab8b524efa3613ef
ms.sourcegitcommit: 5b475c1855b32cf78d2d1bbb4295e4c236f39464
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/24/2020
ms.locfileid: "91158414"
---
# <a name="how-to-generate-the-object-model-in-visual-basic-or-c"></a>Cómo: generar el modelo de objetos en Visual Basic o C\#

En [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)], un modelo de objetos en un lenguaje de programación se asigna a una base de datos relacional. Hay dos herramientas disponibles para generar automáticamente un Visual Basic o un modelo de C# a partir de los metadatos de una base de datos existente.  
  
- Si usa Visual Studio, puede usar la Object Relational Designer para generar un modelo de objetos. Object Relational Designer proporciona una interfaz de usuario enriquecida para ayudarle a generar un [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] modelo de objetos. Para obtener más información, vea [herramientas de LINQ to SQL en Visual Studio](/visualstudio/data-tools/linq-to-sql-tools-in-visual-studio2).
  
- Herramienta de línea de comandos SQLMetal Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
    > [!NOTE]
    > Si no tiene una base de datos existente y desear crear una a partir de un modelo de objetos, puede crear el modelo de objetos mediante el editor de código y <xref:System.Data.Linq.DataContext.CreateDatabase%2A>. Para obtener más información, consulte [Cómo: crear dinámicamente una base de datos](how-to-dynamically-create-a-database.md).  
  
 En la documentación de O/R Designer se proporcionan ejemplos de cómo generar un modelo de objetos de Visual Basic o C# con Object Relational Designer. En la información siguiente se proporcionan ejemplos del uso de la herramienta de línea de comandos de SQLMetal. Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Ejemplo  

 La línea de comandos de SQLMetal mostrada en el ejemplo siguiente genera código Visual Basic como el modelo de objetos basado en atributos de la base de datos de ejemplo Northwind. Se presentan también los procedimientos almacenados y las funciones.  
  
```console  
sqlmetal /code:northwind.vb /language:vb "c:\northwnd.mdf" /sprocs /functions  
```  
  
## <a name="example"></a>Ejemplo  

 La línea de comandos de SQLMetal mostrada en el ejemplo siguiente genera código de C# como el modelo de objetos basado en atributos de la base de datos de ejemplo Northwind. Se presentan también los procedimientos almacenados y las funciones, y los nombres de tabla se pluralizan automáticamente.  
  
```console  
sqlmetal /code:northwind.cs /language:csharp "c:\northwnd.mdf" /sprocs /functions /pluralize  
```  
  
## <a name="see-also"></a>Vea también

- [Guía de programación](programming-guide.md)
- [El modelo de objetos de LINQ to SQL](the-linq-to-sql-object-model.md)
- [Aprender con tutoriales](learning-by-walkthroughs.md)
- [Procedimiento para personalizar clases de entidades con el editor de código](how-to-customize-entity-classes-by-using-the-code-editor.md)
- [Asignación basada en atributos](attribute-based-mapping.md)
- [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [Asignación externa](external-mapping.md)
- [Descargar bases de datos de ejemplo](downloading-sample-databases.md)
- [Crear el modelo de objetos](creating-the-object-model.md)
