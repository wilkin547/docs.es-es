---
title: "Cómo: Generar código personalizado modificando un archivo DBML"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-ado
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 50ad597a-8598-42d3-82dd-fc7d702ebc37
caps.latest.revision: "2"
author: JennieHubbard
ms.author: jhubbard
manager: jhubbard
ms.workload: dotnet
ms.openlocfilehash: efff585cff127e71e2dedd8abf2f502ca28e8df7
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-generate-customized-code-by-modifying-a-dbml-file"></a>Cómo: Generar código personalizado modificando un archivo DBML
Puede generar [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] o código fuente de C# desde un archivo de metadatos base de datos (.dbml) de lenguaje de marcado. Este enfoque proporciona una oportunidad de personalizar el archivo .dbml predeterminado antes de generar el código de asignación de la aplicación. Ésta es una característica avanzada.  
  
 Los pasos de este proceso son los siguientes.  
  
1.  Genere un archivo .dbml.  
  
2.  Utilice un editor para modificar el archivo .dbml. Tenga en cuenta que el archivo .dbml debe validarse con el archivo de esquema (.xsd) de definición para [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] archivos .dbml. Para obtener más información, consulte [generación de código en LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md).  
  
3.  Genere el código fuente de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] o de C#.  
  
 En los ejemplos siguientes se utiliza la herramienta de línea de comandos SQLMetal. Para obtener más información, vea [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md).  
  
## <a name="example"></a>Ejemplo  
 El código siguiente genera un archivo .dbml a partir de la base de datos de ejemplo Northwind. Como origen de los metadatos de la base de datos, puede utilizar el nombre de la base de datos o el nombre del archivo .mdf.  
  
```  
sqlmetal /server:myserver /database:northwind /dbml:mymeta.dbml  
sqlmetal /dbml:mymeta.dbml mydbfile.mdf  
```  
  
## <a name="example"></a>Ejemplo  
 El código siguiente genera un archivo de código fuente de [!INCLUDE[vbprvb](../../../../../../includes/vbprvb-md.md)] o C# a partir de un archivo .dbml.  
  
```  
sqlmetal /namespace:nwind /code:nwind.vb /language:vb DBMLFile.dbml  
sqlmetal /namespace:nwind /code:nwind.cs /language:csharp DBMLFile.dbml  
```  
  
## <a name="see-also"></a>Vea también  
 [Generación de código en LINQ to SQL](../../../../../../docs/framework/data/adonet/sql/linq/code-generation-in-linq-to-sql.md)  
 [SqlMetal.exe (Herramienta de generación de código)](../../../../../../docs/framework/tools/sqlmetal-exe-code-generation-tool.md)  
 [Creación del modelo de objetos](../../../../../../docs/framework/data/adonet/sql/linq/creating-the-object-model.md)
