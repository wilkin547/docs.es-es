---
title: Procedimiento para generar código personalizado mediante la modificación de un archivo DBML
ms.date: 03/30/2017
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
ms.openlocfilehash: 01890e6b899db6b70049e2d6b8193e5b0f4095fb
ms.sourcegitcommit: d2e1dfa7ef2d4e9ffae3d431cf6a4ffd9c8d378f
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/07/2019
ms.locfileid: "70781985"
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a>Procedimiento para generar código personalizado mediante la modificación de un archivo DBML
Puede generar Visual Basic o C# código fuente a partir de un archivo de metadatos de lenguaje de marcado de base de datos (. dbml). Este enfoque proporciona una oportunidad de personalizar el archivo .dbml predeterminado antes de generar el código de asignación de la aplicación. Ésta es una característica avanzada.  
  
 Los pasos de este proceso son los siguientes.  
  
1. Genere un archivo .dbml.  
  
2. Utilice un editor para modificar el archivo .dbml. Tenga en cuenta que el archivo. dbml debe validarse con el archivo de definición de esquema [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] (. xsd) para los archivos. dbml. Para obtener más información, vea [generación de código en LINQ to SQL](code-generation-in-linq-to-sql.md).  
  
3. Generar el Visual Basic o C# código fuente.  
  
 En los ejemplos siguientes se utiliza la herramienta de línea de comandos SQLMetal. Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Ejemplo  
 El código siguiente genera un archivo .dbml a partir de la base de datos de ejemplo Northwind. Como origen de los metadatos de la base de datos, puede utilizar el nombre de la base de datos o el nombre del archivo .mdf.  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a>Ejemplo  
 El código siguiente genera Visual Basic o C# un archivo de código fuente a partir de un archivo. dbml.  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a>Vea también

- [Generación de código en LINQ to SQL](code-generation-in-linq-to-sql.md)
- [SqlMetal.exe (Herramienta de generación de código)](../../../../tools/sqlmetal-exe-code-generation-tool.md)
- [Creación del modelo de objetos](creating-the-object-model.md)
