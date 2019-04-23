---
title: Procedimiento para generar código personalizado mediante la modificación de un archivo DBML
ms.date: 03/30/2017
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
ms.openlocfilehash: c3fa4d9db4076309ab7d6066cc7072797eaead54
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: es-ES
ms.lasthandoff: 04/18/2019
ms.locfileid: "59338428"
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a>Procedimiento para generar código personalizado mediante la modificación de un archivo DBML
Puede generar Visual Basic o C# código fuente a partir de un archivo de metadatos base de datos (.dbml) de lenguaje de marcado. Este enfoque proporciona una oportunidad de personalizar el archivo .dbml predeterminado antes de generar el código de asignación de la aplicación. Ésta es una característica avanzada.  
  
 Los pasos de este proceso son los siguientes.  
  
1. Genere un archivo .dbml.  
  
2. Utilice un editor para modificar el archivo .dbml. Tenga en cuenta que el archivo .dbml debe validarse con el archivo de definición (.xsd) de esquema para [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] archivos .dbml. Para obtener más información, consulte [generación de código en LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
3. Generar el de Visual Basic o C# código fuente.  
  
 En los ejemplos siguientes se utiliza la herramienta de línea de comandos SQLMetal. Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Ejemplo  
 El código siguiente genera un archivo .dbml a partir de la base de datos de ejemplo Northwind. Como origen de los metadatos de la base de datos, puede utilizar el nombre de la base de datos o el nombre del archivo .mdf.  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a>Ejemplo  
 El código siguiente genera el Visual Basic o C# archivo de código fuente desde un archivo dbml.  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a>Vea también

- [Generación de código en LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)
- [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)
- [Creación del modelo de objetos](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
